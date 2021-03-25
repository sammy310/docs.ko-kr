---
title: 메서드 - C# 가이드
description: 메서드, 메서드 매개 변수 및 메서드 반환 값의 개요
ms.technology: csharp-fundamentals
ms.date: 03/16/2021
ms.assetid: 577a8527-1081-4b36-9b9e-0685b6553c6e
ms.openlocfilehash: 5d7f654ca268deff4a0c8e69b76e4d636d2f495e
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "104652934"
---
# <a name="methods-in-c"></a><span data-ttu-id="9dcd3-103">메서드(C#)</span><span class="sxs-lookup"><span data-stu-id="9dcd3-103">Methods in (C#)</span></span>

<span data-ttu-id="9dcd3-104">메서드는 일련의 문을 포함하는 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-104">A method is a code block that contains a series of statements.</span></span> <span data-ttu-id="9dcd3-105">프로그램을 통해 메서드를 호출하고 필요한 메서드 인수를 지정하여 문을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-105">A program causes the statements to be executed by calling the method and specifying any required method arguments.</span></span> <span data-ttu-id="9dcd3-106">C#에서는 실행된 모든 명령이 메서드의 컨텍스트에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-106">In C#, every executed instruction is performed in the context of a method.</span></span> <span data-ttu-id="9dcd3-107">`Main` 메서드는 모든 C# 애플리케이션의 진입점이고 프로그램이 시작될 때 CLR(공용 언어 런타임)에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-107">The `Main` method is the entry point for every C# application and it is called by the common language runtime (CLR) when the program is started.</span></span>

> [!NOTE]
> <span data-ttu-id="9dcd3-108">이 항목에서는 명명된 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-108">This topic discusses named methods.</span></span> <span data-ttu-id="9dcd3-109">익명 함수에 대한 자세한 내용은 [익명 함수](programming-guide/statements-expressions-operators/anonymous-functions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-109">For information about anonymous functions, see [Anonymous Functions](programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>

<a name="signatures"></a>

## <a name="method-signatures"></a><span data-ttu-id="9dcd3-110">메서드 시그니처</span><span class="sxs-lookup"><span data-stu-id="9dcd3-110">Method signatures</span></span>

<span data-ttu-id="9dcd3-111">메서드는 다음을 지정하여 `class` 또는 `struct`에서 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-111">Methods are declared in a `class` or `struct` by specifying:</span></span>

- <span data-ttu-id="9dcd3-112">`public` 또는 `private`와 같은 선택적 액세스 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-112">An optional access level, such as `public` or `private`.</span></span> <span data-ttu-id="9dcd3-113">기본값은 `private`입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-113">The default is `private`.</span></span>
- <span data-ttu-id="9dcd3-114">`abstract` 또는 `sealed`와 같은 선택적 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-114">Optional modifiers such as `abstract` or `sealed`.</span></span>
- <span data-ttu-id="9dcd3-115">반환 값 또는 메서드에 반환 값이 없는 경우 `void`입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-115">The return value, or `void` if the method has none.</span></span>
- <span data-ttu-id="9dcd3-116">메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-116">The method name.</span></span>
- <span data-ttu-id="9dcd3-117">메서드 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-117">Any method parameters.</span></span> <span data-ttu-id="9dcd3-118">메서드 매개 변수는 괄호로 묶고 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-118">Method parameters are enclosed in parentheses and are separated by commas.</span></span> <span data-ttu-id="9dcd3-119">빈 괄호는 메서드에 매개 변수가 필요하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-119">Empty parentheses indicate that the method requires no parameters.</span></span>

<span data-ttu-id="9dcd3-120">이러한 부분이 결합되어 메서드 시그니처를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-120">These parts together form the method signature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9dcd3-121">메서드의 반환 값은 메서드 오버로드를 위한 메서드 서명의 파트가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-121">A return type of a method is not part of the signature of the method for the purposes of method overloading.</span></span> <span data-ttu-id="9dcd3-122">그러나 대리자와 대리자가 가리키는 메서드 간의 호환성을 결정할 경우에는 메서드 서명의 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-122">However, it is part of the signature of the method when determining the compatibility between a delegate and the method that it points to.</span></span>

<span data-ttu-id="9dcd3-123">다음 예제에서는 다섯 개의 메서드를 포함하는 `Motorcycle`이라는 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-123">The following example defines a class named `Motorcycle` that contains five methods:</span></span>

[!code-csharp[csSnippets.Methods#40](../../samples/snippets/csharp/concepts/methods/methods40.cs#40)]

<span data-ttu-id="9dcd3-124">`Motorcycle` 클래스에는 오버로드된 메서드 `Drive`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-124">Note that the `Motorcycle` class includes an overloaded method, `Drive`.</span></span> <span data-ttu-id="9dcd3-125">두 메서드는 이름이 같지만 해당 매개 변수 형식으로 구별되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-125">Two methods have the same name, but must be differentiated by their parameter types.</span></span>

<a name="invocation"></a>

## <a name="method-invocation"></a><span data-ttu-id="9dcd3-126">메서드 호출</span><span class="sxs-lookup"><span data-stu-id="9dcd3-126">Method invocation</span></span>

<span data-ttu-id="9dcd3-127">메서드는 *인스턴스* 또는 *정적* 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-127">Methods can be either *instance* or *static*.</span></span> <span data-ttu-id="9dcd3-128">인스턴스 메서드를 호출하려면 개체를 인스턴스화하고 해당 개체에서 메서드를 호출해야 합니다. 인스턴스 메서드는 인스턴스 및 해당 데이터에 대해 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-128">Invoking an instance method requires that you instantiate an object and call the method on that object; an instance method operates on that instance and its data.</span></span> <span data-ttu-id="9dcd3-129">메서드가 속하는 형식의 이름을 참조하여 정적 메서드를 호출합니다. 정적 메서드는 인스턴스 데이터에 대해 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-129">You invoke a static method by referencing the name of the type to which the method belongs; static methods do not operate on instance data.</span></span> <span data-ttu-id="9dcd3-130">개체 인스턴스를 통해 정적 메서드를 호출하려고 하면 컴파일러 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-130">Attempting to call a static method through an object instance generates a compiler error.</span></span>

<span data-ttu-id="9dcd3-131">메서드 호출은 필드 액세스와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-131">Calling a method is like accessing a field.</span></span> <span data-ttu-id="9dcd3-132">개체 이름(인스턴스 메서드를 호출하는 경우) 또는 형식 이름(`static` 메서드를 호출하는 경우) 뒤에 마침표, 메서드 이름 및 괄호를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-132">After the object name (if you are calling an instance method) or the type name (if you are calling a `static` method), add a period, the name of the method, and parentheses.</span></span> <span data-ttu-id="9dcd3-133">인수는 괄호 안에 나열되고 쉼표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-133">Arguments are listed within the parentheses and are separated by commas.</span></span>

<span data-ttu-id="9dcd3-134">메서드 정의는 필요한 모든 매개 변수의 이름 및 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-134">The method definition specifies the names and types of any parameters that are required.</span></span> <span data-ttu-id="9dcd3-135">호출자는 메서드를 호출할 때 각 매개 변수에 대해 인수라는 구체적인 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-135">When a caller invokes the method, it provides concrete values, called arguments, for each parameter.</span></span> <span data-ttu-id="9dcd3-136">인수는 매개 변수 형식과 호환되어야 하지만 인수 이름(호출하는 코드에 사용된 경우)은 메서드에 정의된 명명된 매개 변수와 동일할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-136">The arguments must be compatible with the parameter type, but the argument name, if one is used in the calling code, does not have to be the same as the parameter named defined in the method.</span></span> <span data-ttu-id="9dcd3-137">다음 예제에서는 `Square` 메서드에 *i* 라는 `int` 형식의 단일 매개 변수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-137">In the following example, the `Square` method includes a single parameter of type `int` named *i*.</span></span> <span data-ttu-id="9dcd3-138">첫 번째 메서드 호출은 `Square` 메서드에 *num* 이라는 `int` 형식의 변수를 전달합니다. 두 번째 호출은 숫자 상수, 세 번째 호출은 식을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-138">The first method call passes the `Square` method a variable of type `int` named *num*; the second, a numeric constant; and the third, an expression.</span></span>

[!code-csharp[csSnippets.Methods#74](../../samples/snippets/csharp/concepts/methods/params74.cs#74)]

<span data-ttu-id="9dcd3-139">가장 일반적인 형태의 메서드 호출은 위치 인수를 사용하며, 메서드 매개 변수와 동일한 순서로 인수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-139">The most common form of method invocation used positional arguments; it supplies arguments in the same order as method parameters.</span></span> <span data-ttu-id="9dcd3-140">`Motorcycle` 클래스의 메서드는 다음 예제와 같이 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-140">The methods of the `Motorcycle` class can therefore be called as in the following example.</span></span> <span data-ttu-id="9dcd3-141">예를 들어 `Drive` 메서드 호출에는 메서드 구문의 두 매개 변수에 해당하는 두 개의 인수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-141">The call to the `Drive` method, for example, includes two arguments that correspond to the two parameters in the method's syntax.</span></span> <span data-ttu-id="9dcd3-142">첫 번째 인수는 `miles` 매개 변수의 값이 되고, 두 번째 인수는 `speed` 매개 변수의 값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-142">The first becomes the value of the `miles` parameter, the second the value of the `speed` parameter.</span></span>

[!code-csharp[csSnippets.Methods#41](../../samples/snippets/csharp/concepts/methods/methods40.cs#41)]

<span data-ttu-id="9dcd3-143">메서드를 호출할 때 위치 인수 대신 ‘명명된 인수’를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-143">You can also use *named arguments* instead of positional arguments when invoking a method.</span></span> <span data-ttu-id="9dcd3-144">명명된 인수를 사용하는 경우 매개 변수 이름 뒤에 콜론(":")과 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-144">When using named arguments, you specify the parameter name followed by a colon (":") and the argument.</span></span> <span data-ttu-id="9dcd3-145">모든 필수 인수가 있기만 하면 메서드의 인수 순서는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-145">Arguments to the method can appear in any order, as long as all required arguments are present.</span></span> <span data-ttu-id="9dcd3-146">다음 예제에서는 명명된 인수를 사용하여 `TestMotorcycle.Drive` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-146">The following example uses named arguments to invoke the `TestMotorcycle.Drive` method.</span></span> <span data-ttu-id="9dcd3-147">이 예제에서는 명명된 인수가 메서드의 매개 변수 목록과 반대 순서로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-147">In this example, the named arguments are passed in the opposite order from the method's parameter list.</span></span>

[!code-csharp[csSnippets.Methods#45](../../samples/snippets/csharp/concepts/methods/named1.cs#45)]

<span data-ttu-id="9dcd3-148">위치 인수와 명명된 인수 둘 다를 사용하여 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-148">You can invoke a method using both positional arguments and named arguments.</span></span> <span data-ttu-id="9dcd3-149">그러나 명명된 인수가 올바른 위치에 있는 경우에만 명명된 인수 뒤에 위치 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-149">However, positional arguments can only follow named arguments when the named arguments are in the correct positions.</span></span> <span data-ttu-id="9dcd3-150">다음 예제에서는 위치 인수 하나와 명명된 인수 하나를 사용하여 이전 예제의 `TestMotorcycle.Drive` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-150">The following example invokes the `TestMotorcycle.Drive` method from the previous example using one positional argument and one named argument.</span></span>

[!code-csharp[csSnippets.Methods#46](../../samples/snippets/csharp/concepts/methods/named2.cs#46)]

<a name="inherited"></a>

## <a name="inherited-and-overridden-methods"></a><span data-ttu-id="9dcd3-151">상속 및 재정의된 메서드</span><span class="sxs-lookup"><span data-stu-id="9dcd3-151">Inherited and overridden methods</span></span>

<span data-ttu-id="9dcd3-152">형식은 해당 형식에서 명시적으로 정의된 멤버 외에도 기본 클래스에서 정의된 멤버를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-152">In addition to the members that are explicitly defined in a type, a type inherits members defined in its base classes.</span></span> <span data-ttu-id="9dcd3-153">관리되는 형식 시스템의 모든 형식이 직접 또는 간접적으로 <xref:System.Object> 클래스에서 상속하므로 모든 형식은 <xref:System.Object.Equals(System.Object)>, <xref:System.Object.GetType> 및 <xref:System.Object.ToString>과 같은 해당 멤버를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-153">Since all types in the managed type system inherit directly or indirectly from the <xref:System.Object> class, all types inherit its members, such as <xref:System.Object.Equals(System.Object)>, <xref:System.Object.GetType>, and <xref:System.Object.ToString>.</span></span> <span data-ttu-id="9dcd3-154">다음 예제에서는 `Person` 클래스를 정의하고, 두 개의 `Person` 개체를 인스턴스화하고, `Person.Equals` 메서드를 호출하여 두 개체가 같은지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-154">The following example defines a `Person` class, instantiates two `Person` objects, and calls the `Person.Equals` method to determine whether the two objects are equal.</span></span> <span data-ttu-id="9dcd3-155">그러나 `Equals` 메서드는 `Person` 클래스에서 정의되지 않고 <xref:System.Object>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-155">The `Equals` method, however, is not defined in the `Person` class; it is inherited from <xref:System.Object>.</span></span>

[!code-csharp[csSnippets.Methods#104](../../samples/snippets/csharp/concepts/methods/inherited1.cs#104)]

<span data-ttu-id="9dcd3-156">형식은 `override` 키워드를 사용하고 재정의된 메서드에 대한 구현을 제공하여 상속된 멤버를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-156">Types can override inherited members by using the `override` keyword and providing an implementation for the overridden method.</span></span> <span data-ttu-id="9dcd3-157">메서드 시그니처는 재정의된 메서드의 시그니처와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-157">The method signature must be the same as that of the overridden method.</span></span> <span data-ttu-id="9dcd3-158">다음 예제는 <xref:System.Object.Equals(System.Object)> 메서드를 재정의한다는 점을 제외하고 이전 예제와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-158">The following example is like the previous one, except that it overrides the <xref:System.Object.Equals(System.Object)> method.</span></span> <span data-ttu-id="9dcd3-159">또한 두 메서드가 일치하는 결과를 제공하기 때문에 <xref:System.Object.GetHashCode> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-159">(It also overrides the <xref:System.Object.GetHashCode> method, since the two methods are intended to provide consistent results.)</span></span>

[!code-csharp[csSnippets.Methods#105](../../samples/snippets/csharp/concepts/methods/overridden1.cs#105)]

<a name="passing"></a>

## <a name="passing-parameters"></a><span data-ttu-id="9dcd3-160">매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="9dcd3-160">Passing parameters</span></span>

<span data-ttu-id="9dcd3-161">C#의 형식은 *값 형식* 또는 *참조 형식* 입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-161">Types in C# are either *value types* or *reference types*.</span></span> <span data-ttu-id="9dcd3-162">기본 제공 값 형식의 목록은 [형식](./tour-of-csharp/types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-162">For a list of built-in value types, see [Types](./tour-of-csharp/types.md).</span></span> <span data-ttu-id="9dcd3-163">기본적으로, 값 형식과 참조 형식은 둘 다 값으로 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-163">By default, both value types and reference types are passed to a method by value.</span></span>

<a name="byval"></a>

### <a name="passing-parameters-by-value"></a><span data-ttu-id="9dcd3-164">값으로 매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="9dcd3-164">Passing parameters by value</span></span>

<span data-ttu-id="9dcd3-165">값 형식이 값으로 메서드에 전달되는 경우 개체 자체가 아니라 개체의 복사본이 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-165">When a value type is passed to a method by value, a copy of the object instead of the object itself is passed to the method.</span></span> <span data-ttu-id="9dcd3-166">따라서 제어가 호출자로 반환될 때 호출된 메서드의 개체 변경 내용은 원래 개체에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-166">Therefore, changes to the object in the called method have no effect on the original object when control returns to the caller.</span></span>

<span data-ttu-id="9dcd3-167">다음 예제에서는 값 형식을 값으로 메서드에 전달하며, 호출된 메서드는 값 형식의 값을 변경하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-167">The following example passes a value type to a method by value, and the called method attempts to change the value type's value.</span></span> <span data-ttu-id="9dcd3-168">값 형식인 `int` 형식의 변수를 정의하고, 해당 값을 20으로 초기화한 다음 `ModifyValue`라는 메서드에 전달하면 이 메서드가 변수의 값을 30으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-168">It defines a variable of type `int`, which is a value type, initializes its value to 20, and passes it to a method named `ModifyValue` that changes the variable's value to 30.</span></span> <span data-ttu-id="9dcd3-169">그러나 메서드가 반환될 때는 변수의 값이 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-169">When the method returns, however, the variable's value remains unchanged.</span></span>

[!code-csharp[csSnippets.Methods#10](../../samples/snippets/csharp/concepts/methods/byvalue10.cs#10)]

<span data-ttu-id="9dcd3-170">참조 형식의 개체가 메서드에 값으로 전달되는 경우 개체에 대한 참조가 값으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-170">When an object of a reference type is passed to a method by value, a reference to the object is passed by value.</span></span> <span data-ttu-id="9dcd3-171">즉, 메서드는 개체 자체가 아니라 개체의 위치를 나타내는 인수를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-171">That is, the method receives not the object itself, but an argument that indicates the location of the object.</span></span> <span data-ttu-id="9dcd3-172">이 참조를 사용하여 개체의 멤버를 변경하는 경우 제어가 호출하는 메서드로 반환될 때 변경 내용이 개체에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-172">If you change a member of the object by using this reference, the change is reflected in the object when control returns to the calling method.</span></span> <span data-ttu-id="9dcd3-173">그러나 메서드에 전달되는 개체를 바꾸면 제어가 호출자로 반환될 때 원래 개체에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-173">However, replacing the object passed to the method has no effect on the original object when control returns to the caller.</span></span>

<span data-ttu-id="9dcd3-174">다음 예제에서는 `SampleRefType`이라는 클래스(참조 형식)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-174">The following example defines a class (which is a reference type) named `SampleRefType`.</span></span> <span data-ttu-id="9dcd3-175">`SampleRefType` 개체를 인스턴스화하고, 해당 `value` 필드에 44를 할당한 다음 개체를 `ModifyObject` 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-175">It instantiates a `SampleRefType` object, assigns 44 to its `value` field, and passes the object to the `ModifyObject` method.</span></span> <span data-ttu-id="9dcd3-176">이 예제는 인수를 값으로 메서드에 전달한다는 점에서 기본적으로 이전 예제와 같은 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-176">This example does essentially the same thing as the previous example -- it passes an argument by value to a method.</span></span> <span data-ttu-id="9dcd3-177">그러나 참조 형식이 사용되므로 결과가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-177">But because a reference type is used, the result is different.</span></span> <span data-ttu-id="9dcd3-178">예제의 출력과 같이 `ModifyObject`에서 `obj.value` 필드에 대해 수정한 내용으로 인해 `Main` 메서드에서 `rt` 인수의 `value` 필드도 33으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-178">The modification that is made in `ModifyObject` to the `obj.value` field also changes the `value` field of the argument, `rt`, in the `Main` method to 33, as the output from the example shows.</span></span>

[!code-csharp[csSnippets.Methods#42](../../samples/snippets/csharp/concepts/methods/byvalue42.cs#42)]

<a name="byref"></a>

### <a name="passing-parameters-by-reference"></a><span data-ttu-id="9dcd3-179">참조로 매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="9dcd3-179">Passing parameters by reference</span></span>

<span data-ttu-id="9dcd3-180">메서드의 인수 값을 변경하고 제어가 호출하는 메서드로 반환될 때 해당 변경 내용을 반영하려는 경우 참조로 매개 변수를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-180">You pass a parameter by reference when you want to change the value of an argument in a method and want to reflect that change when control returns to the calling method.</span></span> <span data-ttu-id="9dcd3-181">참조로 매개 변수를 전달하려면 [`ref`](language-reference/keywords/ref.md) 또는 [`out`](language-reference/keywords/out-parameter-modifier.md) 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-181">To pass a parameter by reference, you use the [`ref`](language-reference/keywords/ref.md) or [`out`](language-reference/keywords/out-parameter-modifier.md) keyword.</span></span> <span data-ttu-id="9dcd3-182">복사를 방지하지만 여전히 [`in`](language-reference/keywords/in-parameter-modifier.md) 키워드를 사용하여 수정을 방지하도록 참조로 값을 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-182">You can also pass a value by reference to avoid copying but still prevent modifications using the [`in`](language-reference/keywords/in-parameter-modifier.md) keyword.</span></span>

<span data-ttu-id="9dcd3-183">다음 예제는 값이 참조로 `ModifyValue` 메서드에 전달된다는 점을 제외하고 이전 예제와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-183">The following example is identical to the previous one, except the value is passed by reference to the `ModifyValue` method.</span></span> <span data-ttu-id="9dcd3-184">`ModifyValue` 메서드에서 매개 변수의 값을 수정하면 제어가 호출자로 반환될 때 값의 변경 내용이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-184">When the value of the parameter is modified in the `ModifyValue` method, the change in value is reflected when control returns to the caller.</span></span>

[!code-csharp[csSnippets.Methods#106](../../samples/snippets/csharp/concepts/methods/byref106.cs#106)]

<span data-ttu-id="9dcd3-185">by ref 매개 변수를 사용하는 일반적인 패턴은 변수 값의 교환을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-185">A common pattern that uses by ref parameters involves swapping the values of variables.</span></span> <span data-ttu-id="9dcd3-186">두 개의 변수를 참조로 메서드에 전달하고 메서드가 해당 내용을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-186">You pass two variables to a method by reference, and the method swaps their contents.</span></span> <span data-ttu-id="9dcd3-187">다음 예제에서는 정수 값을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-187">The following example swaps integer values.</span></span>

[!code-csharp[csSnippets.Methods#106](../../samples/snippets/csharp/concepts/methods/swap107.cs#107)]

<span data-ttu-id="9dcd3-188">참조 형식 매개 변수를 전달하면 해당 개별 요소 또는 필드의 값이 아니라 참조 자체의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-188">Passing a reference-type parameter allows you to change the value of the reference itself, rather than the value of its individual elements or fields.</span></span>

<a name="paramarray"></a>

### <a name="parameter-arrays"></a><span data-ttu-id="9dcd3-189">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="9dcd3-189">Parameter arrays</span></span>

<span data-ttu-id="9dcd3-190">경우에 따라 메서드의 인수 개수를 정확하게 지정하라는 요구 사항은 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-190">Sometimes, the requirement that you specify the exact number of arguments to your method is restrictive.</span></span> <span data-ttu-id="9dcd3-191">`params` 키워드를 사용하여 매개 변수를 매개 변수 배열로 지정하면 가변 개수의 인수로 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-191">By using the `params` keyword to indicate that a parameter is a parameter array, you allow your method to be called with a variable number of arguments.</span></span> <span data-ttu-id="9dcd3-192">`params` 키워드로 태그가 지정된 매개 변수는 배열 형식이어야 하며, 메서드의 매개 변수 목록에서 마지막 매개 변수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-192">The parameter tagged with the `params` keyword must be an array type, and it must be the last parameter in the method's parameter list.</span></span>

<span data-ttu-id="9dcd3-193">그러면 호출자가 다음 네 가지 방법 중 하나로 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-193">A caller can then invoke the method in either of four ways:</span></span>

- <span data-ttu-id="9dcd3-194">원하는 개수의 요소를 포함하는 적절한 형식의 배열 전달</span><span class="sxs-lookup"><span data-stu-id="9dcd3-194">By passing an array of the appropriate type that contains the desired number of elements.</span></span>
- <span data-ttu-id="9dcd3-195">적절한 형식의 개별 인수가 포함된 쉼표로 구분된 목록을 메서드에 전달</span><span class="sxs-lookup"><span data-stu-id="9dcd3-195">By passing a comma-separated list of individual arguments of the appropriate type to the method.</span></span>
- <span data-ttu-id="9dcd3-196">`null`을 전달</span><span class="sxs-lookup"><span data-stu-id="9dcd3-196">By passing `null`.</span></span>
- <span data-ttu-id="9dcd3-197">매개 변수 배열에 인수 제공 안 함</span><span class="sxs-lookup"><span data-stu-id="9dcd3-197">By not providing an argument to the parameter array.</span></span>

<span data-ttu-id="9dcd3-198">다음 예제에서는 매개 변수 배열의 모든 모음을 반환하는 `GetVowels` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-198">The following example defines a method named `GetVowels` that returns all the vowels from a parameter array.</span></span> <span data-ttu-id="9dcd3-199">`Main` 메서드는 해당 메서드를 호출하는 네 가지 방법을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-199">The `Main` method illustrates all four ways of invoking the method.</span></span> <span data-ttu-id="9dcd3-200">호출자가 `params` 한정자를 포함하는 매개 변수의 인수를 제공할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-200">Callers are not required to supply any arguments for parameters that include the `params` modifier.</span></span> <span data-ttu-id="9dcd3-201">이 경우 매개 변수는 빈 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-201">In that case, the parameter is an empty array.</span></span>

[!code-csharp[csSnippets.Methods#75](~/samples/snippets/csharp/concepts/methods/params75.cs#75)]

<a name="optional"></a>

## <a name="optional-parameters-and-arguments"></a><span data-ttu-id="9dcd3-202">선택적 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="9dcd3-202">Optional parameters and arguments</span></span>

<span data-ttu-id="9dcd3-203">메서드 정의에서 해당 매개 변수를 필수 또는 선택 사항으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-203">A method definition can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="9dcd3-204">기본적으로 매개 변수는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-204">By default, parameters are required.</span></span> <span data-ttu-id="9dcd3-205">선택적 매개 변수는 메서드 정의에 매개 변수의 기본값을 포함하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-205">Optional parameters are specified by including the parameter's default value in the method definition.</span></span> <span data-ttu-id="9dcd3-206">메서드를 호출할 때 선택적 매개 변수에 대한 인수가 제공되지 않은 경우 기본값이 대신 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-206">When the method is called, if no argument is supplied for an optional parameter, the default value is used instead.</span></span>

<span data-ttu-id="9dcd3-207">다음 종류의 식 중 하나로 매개 변수의 기본값을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-207">The parameter's default value must be assigned by one of the following kinds of expressions:</span></span>

- <span data-ttu-id="9dcd3-208">리터럴 문자열이나 숫자와 같은 상수</span><span class="sxs-lookup"><span data-stu-id="9dcd3-208">A constant, such as a literal string or number.</span></span>
- <span data-ttu-id="9dcd3-209">`new ValType()` 형태의 식. 여기서 `ValType`은 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-209">An expression of the form `new ValType()`, where `ValType` is a value type.</span></span> <span data-ttu-id="9dcd3-210">이 경우 형식의 실제 멤버가 아닌 값 형식의 매개 변수가 없는 암시적 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-210">Note that this invokes the value type's implicit parameterless constructor, which is not an actual member of the type.</span></span>
- <span data-ttu-id="9dcd3-211">`default(ValType)` 형태의 식. 여기서 `ValType`은 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-211">An expression of the form `default(ValType)`, where `ValType` is a value type.</span></span>

<span data-ttu-id="9dcd3-212">메서드에 필수 및 선택적 매개 변수가 둘 다 포함된 경우 선택적 매개 변수는 매개 변수 목록의 끝에서 모든 필수 매개 변수 다음에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-212">If a method includes both required and optional parameters, optional parameters are defined at the end of the parameter list, after all required parameters.</span></span>

<span data-ttu-id="9dcd3-213">다음 예제에서는 필수 매개 변수 하나와 선택적 매개 변수 두 개가 있는 `ExampleMethod` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-213">The following example defines a method, `ExampleMethod`, that has one required and two optional parameters.</span></span>

[!code-csharp[csSnippets.Methods#21](../../samples/snippets/csharp/concepts/methods/optional1.cs#21)]

<span data-ttu-id="9dcd3-214">여러 선택적 인수가 있는 메서드를 위치 인수로 호출하는 경우 호출자가 첫 번째 매개 변수부터 인수가 제공되는 마지막 매개 변수까지 모든 선택적 매개 변수에 대한 인수를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-214">If a method with multiple optional arguments is invoked using positional arguments, the caller must supply an argument for all optional parameters from the first one to the last one for which an argument is supplied.</span></span> <span data-ttu-id="9dcd3-215">예를 들어 `ExampleMethod` 메서드에서 호출자가 `description` 매개 변수에 대한 인수를 제공하는 경우 `optionalInt` 매개 변수에 대한 인수도 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-215">In the case of the  `ExampleMethod` method, for example, if the caller supplies an argument for the `description` parameter, it must also supply one for the `optionalInt` parameter.</span></span> <span data-ttu-id="9dcd3-216">`opt.ExampleMethod(2, 2, "Addition of 2 and 2");`는 유효한 메서드 호출이고, `opt.ExampleMethod(2, , "Addition of 2 and 0");`은 "인수가 없습니다." 컴파일러 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-216">`opt.ExampleMethod(2, 2, "Addition of 2 and 2");` is a valid method call; `opt.ExampleMethod(2, , "Addition of 2 and 0");` generates an "Argument missing" compiler error.</span></span>

<span data-ttu-id="9dcd3-217">명명된 인수 또는 위치 인수와 명명된 인수의 조합을 사용하여 메서드를 호출하는 경우 호출자는 메서드 호출에서 마지막 위치 인수 뒤에 오는 모든 인수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-217">If a method is called using named arguments or a combination of positional and named arguments, the caller can omit any arguments that follow the last positional argument in the method call.</span></span>

<span data-ttu-id="9dcd3-218">다음 예제에서는 `ExampleMethod` 메서드를 세 번 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-218">The following example calls the `ExampleMethod` method three times.</span></span>  <span data-ttu-id="9dcd3-219">처음 두 메서드 호출은 위치 인수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-219">The first two method calls use positional arguments.</span></span> <span data-ttu-id="9dcd3-220">첫 번째 호출은 선택적 인수를 둘 다 생략하고, 두 번째 호출은 마지막 인수를 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-220">The first omits both optional arguments, while the second omits the last argument.</span></span> <span data-ttu-id="9dcd3-221">세 번째 메서드 호출은 필수 매개 변수에 대한 위치 인수를 제공하지만 `optionalInt` 인수를 생략하고 명명된 인수를 사용하여 `description` 매개 변수에 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-221">The third method call supplies a positional argument for the required parameter but uses a named argument to supply a value to the `description` parameter while omitting the `optionalInt` argument.</span></span>

[!code-csharp[csSnippets.Methods#22](../../samples/snippets/csharp/concepts/methods/optional1.cs#22)]

<span data-ttu-id="9dcd3-222">선택적 매개 변수를 사용하면 *오버로드 확인* 또는 C# 컴파일러가 메서드 호출에서 호출해야 하는 특정 오버로드를 확인하는 방법이 다음과 같이 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-222">The use of optional parameters affects *overload resolution*, or the way in which the C# compiler determines which particular overload should be invoked by a method call, as follows:</span></span>

- <span data-ttu-id="9dcd3-223">메서드, 인덱서 또는 생성자는 해당 매개 변수가 각각 선택 사항이거나 이름 또는 위치로 호출하는 문의 단일 인수에 해당하고 이 인수를 매개 변수의 형식으로 변환할 수 있는 경우 실행 후보가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-223">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>
- <span data-ttu-id="9dcd3-224">둘 이상의 인증서가 있으면 기본 설정 변환에 대한 오버로드 확인 규칙이 명시적으로 지정된 인수에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-224">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="9dcd3-225">선택적 매개 변수에 대해 생략된 인수는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-225">Omitted arguments for optional parameters are ignored.</span></span>
- <span data-ttu-id="9dcd3-226">두 후보가 똑같이 정상이라고 판단되는 경우 기본적으로 호출에서 인수가 생략된 선택적 매개 변수가 없는 후보가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-226">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="9dcd3-227">이는 매개 변수가 적은 후보에 대한 오버로드 확인에서 일반적인 기본 설정의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-227">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>

<a name="return"></a>

## <a name="return-values"></a><span data-ttu-id="9dcd3-228">반환 값</span><span class="sxs-lookup"><span data-stu-id="9dcd3-228">Return values</span></span>

<span data-ttu-id="9dcd3-229">메서드는 호출자에 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-229">Methods can return a value to the caller.</span></span> <span data-ttu-id="9dcd3-230">메서드 이름 앞에 나열된 반환 형식이 `void`가 아니면 메서드는 `return` 키워드를 사용하여 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-230">If the return type (the type listed before the method name) is not `void`, the method can return the value by using the `return` keyword.</span></span> <span data-ttu-id="9dcd3-231">`return` 키워드에 이어 반환 형식과 일치하는 변수, 상수 또는 식을 포함하는 문은 메서드 호출자에 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-231">A statement with the `return` keyword followed by a variable, constant, or expression that matches the return type will return that value to the method caller.</span></span> <span data-ttu-id="9dcd3-232">`return` 키워드를 사용하여 값을 반환하려면 void가 아닌 반환 값을 포함한 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-232">Methods with a non-void return type are required to use the `return` keyword to return a value.</span></span> <span data-ttu-id="9dcd3-233">`return` 키워드는 메서드 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-233">The `return` keyword also stops the execution of the method.</span></span>

<span data-ttu-id="9dcd3-234">반환 형식이 `void`이면 값이 없는 `return` 문을 사용하여 메서드 실행을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-234">If the return type is `void`, a `return` statement without a value is still useful to stop the execution of the method.</span></span> <span data-ttu-id="9dcd3-235">`return` 키워드를 사용하지 않으면 메서드는 코드 블록 끝에 도달할 때 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-235">Without the `return` keyword, the method will stop executing when it reaches the end of the code block.</span></span>

<span data-ttu-id="9dcd3-236">예를 들어 이들 두 메서드에서는 `return` 키워드를 사용하여 정수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-236">For example, these two methods use the `return` keyword to return integers:</span></span>

[!code-csharp[csSnippets.Methods#44](../../samples/snippets/csharp/concepts/methods/return44.cs#44)]

<span data-ttu-id="9dcd3-237">메서드에서 반환된 값을 사용하려면 호출하는 메서드에서 같은 형식의 값으로 충분한 모든 경우에 메서드 호출 자체를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-237">To use a value returned from a method, the calling method can use the method call itself anywhere a value of the same type would be sufficient.</span></span> <span data-ttu-id="9dcd3-238">반환 값을 변수에 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-238">You can also assign the return value to a variable.</span></span> <span data-ttu-id="9dcd3-239">예를 들어 다음 두 코드 예제에서는 같은 목표를 달성합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-239">For example, the following two code examples accomplish the same goal:</span></span>

[!code-csharp[csSnippets.Methods#45](../../samples/snippets/csharp/concepts/methods/return44.cs#45)]

[!code-csharp[csSnippets.Methods#46](../../samples/snippets/csharp/concepts/methods/return44.cs#46)]

<span data-ttu-id="9dcd3-240">지역 변수(이 경우 `result`)를 사용하여 값을 저장하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-240">Using a local variable, in this case, `result`, to store a value is optional.</span></span> <span data-ttu-id="9dcd3-241">코드의 가독성에 도움이 될 수 있고 전체 메서드 범위에 대해 인수의 원래 값을 저장해야 할 경우 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-241">It may help the readability of the code, or it may be necessary if you need to store the original value of the argument for the entire scope of the method.</span></span>

<span data-ttu-id="9dcd3-242">메서드에서 둘 이상의 값을 반환하려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-242">Sometimes, you want your method to return more than a single value.</span></span> <span data-ttu-id="9dcd3-243">C# 7.0부터 *튜플 형식* 및 *튜플 리터럴* 을 사용하면 이 작업을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-243">Starting with C# 7.0, you can do this easily by using *tuple types* and *tuple literals*.</span></span> <span data-ttu-id="9dcd3-244">튜플 형식은 튜플 요소의 데이터 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-244">The tuple type defines the data types of the tuple's elements.</span></span> <span data-ttu-id="9dcd3-245">튜플 리터럴은 반환된 튜플의 실제 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-245">Tuple literals provide the actual values of the returned tuple.</span></span> <span data-ttu-id="9dcd3-246">다음 예제에서 `(string, string, string, int)`는 `GetPersonalInfo` 메서드에서 반환되는 튜플 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-246">In the following example, `(string, string, string, int)` defines the tuple type that is returned by the `GetPersonalInfo` method.</span></span> <span data-ttu-id="9dcd3-247">`(per.FirstName, per.MiddleName, per.LastName, per.Age)` 식은 튜플 리터럴입니다. 메서드는 `PersonInfo` 개체와 함께 이름, 중간 이름 및 성을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-247">The expression `(per.FirstName, per.MiddleName, per.LastName, per.Age)` is the tuple literal; the method returns the first, middle, and last name, along with the age, of a `PersonInfo` object.</span></span>

```csharp
public (string, string, string, int) GetPersonalInfo(string id)
{
    PersonInfo per = PersonInfo.RetrieveInfoById(id);
    return (per.FirstName, per.MiddleName, per.LastName, per.Age);
}
```

<span data-ttu-id="9dcd3-248">호출자는 반환된 튜플을 코드에서 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-248">The caller can then consume the returned tuple with code like the following:</span></span>

```csharp
var person = GetPersonalInfo("111111111")
Console.WriteLine($"{person.Item1} {person.Item3}: age = {person.Item4}");
```

<span data-ttu-id="9dcd3-249">튜플 형식 정의의 튜플 요소에 이름을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-249">Names can also be assigned to the tuple elements in the tuple type definition.</span></span> <span data-ttu-id="9dcd3-250">다음 예제에서는 명명된 요소를 사용하는 `GetPersonalInfo` 메서드의 대체 버전을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-250">The following example shows an alternate version of the `GetPersonalInfo` method that uses named elements:</span></span>

```csharp
public (string FName, string MName, string LName, int Age) GetPersonalInfo(string id)
{
    PersonInfo per = PersonInfo.RetrieveInfoById(id);
    return (per.FirstName, per.MiddleName, per.LastName, per.Age);
}
```

<span data-ttu-id="9dcd3-251">`GetPersonInfo` 메서드에 대한 이전 호출을 다음과 같이 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-251">The previous call to the `GetPersonInfo` method can then be modified as follows:</span></span>

```csharp
var person = GetPersonalInfo("111111111");
Console.WriteLine($"{person.FName} {person.LName}: age = {person.Age}");
```

<span data-ttu-id="9dcd3-252">메서드에 배열이 인수로 전달되고 메서드가 개별 요소의 값을 수정하는 경우 값의 스타일 또는 기능 흐름 개선을 위해 메서드에서 배열을 반환하도록 선택할 수도 있지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-252">If a method is passed an array as an argument and modifies the value of individual elements, it is not necessary for the method to return the array, although you may choose to do so for good style or functional flow of values.</span></span>  <span data-ttu-id="9dcd3-253">이는 C#에서 모든 참조 형식을 값으로 전달하고 배열 참조의 값이 배열에 대한 포인터이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-253">This is because C# passes all reference types by value, and the value of an array reference is the pointer to the array.</span></span> <span data-ttu-id="9dcd3-254">다음 예제에서는 `DoubleValues` 메서드에서 수행한 `values` 배열 내용의 변경 사항을 배열에 대한 참조가 있는 모든 코드에서 관찰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-254">In the following example, changes to the contents of the `values` array that are made in the `DoubleValues` method are observable by any code that has a reference to the array.</span></span>

[!code-csharp[csSnippets.Methods#101](../../samples/snippets/csharp/concepts/methods/returnarray1.cs#101)]

<a name="extension"></a>

## <a name="extension-methods"></a><span data-ttu-id="9dcd3-255">확장 메서드</span><span class="sxs-lookup"><span data-stu-id="9dcd3-255">Extension methods</span></span>

<span data-ttu-id="9dcd3-256">일반적으로 기존 형식에 메서드를 추가하는 방법에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-256">Ordinarily, there are two ways to add a method to an existing type:</span></span>

- <span data-ttu-id="9dcd3-257">해당 형식에 대한 소스 코드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-257">Modify the source code for that type.</span></span> <span data-ttu-id="9dcd3-258">물론, 형식의 소스 코드를 소유하지 않은 경우에는 이 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-258">You cannot do this, of course, if you do not own the type's source code.</span></span> <span data-ttu-id="9dcd3-259">이는 메서드를 지원하기 위해 전용 데이터 필드를 추가하는 경우에도 주요 변경 내용이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-259">And this becomes a breaking change if you also add any private data fields to support the method.</span></span>
- <span data-ttu-id="9dcd3-260">파생 클래스에서 새 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-260">Define the new method in a derived class.</span></span> <span data-ttu-id="9dcd3-261">구조체, 열거형 등의 다른 형식에 대해 상속을 사용하여 이러한 방식으로 메서드를 추가할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-261">A method cannot be added in this way using inheritance for other types, such as structures and enumerations.</span></span> <span data-ttu-id="9dcd3-262">봉인 클래스에 메서드를 "추가"하는 데 사용할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-262">Nor can it be used to "add" a method to a sealed class.</span></span>

<span data-ttu-id="9dcd3-263">확장 메서드를 사용하면 형식 자체를 수정하거나 상속된 형식에서 새 메서드를 구현하지 않고 기존 형식에 메서드를 "추가"할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-263">Extension methods let you "add" a method to an existing type without modifying the type itself or implementing the new method in an inherited type.</span></span> <span data-ttu-id="9dcd3-264">또한 확장 메서드는 확장하는 형식과 동일한 어셈블리에 있지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-264">The extension method also does not have to reside in the same assembly as the type it extends.</span></span> <span data-ttu-id="9dcd3-265">형식의 정의된 멤버인 것처럼 확장 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-265">You call an extension method as if it were a defined member of a type.</span></span>

<span data-ttu-id="9dcd3-266">자세한 내용은 [확장 메서드](programming-guide/classes-and-structs/extension-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-266">For more information, see [Extension Methods](programming-guide/classes-and-structs/extension-methods.md).</span></span>

<a name="async"></a>

## <a name="async-methods"></a><span data-ttu-id="9dcd3-267">비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="9dcd3-267">Async Methods</span></span>

<span data-ttu-id="9dcd3-268">비동기 기능을 사용하면 명시적 콜백을 사용하거나 수동으로 여러 메서드 또는 람다 식에 코드를 분할하지 않고도 비동기 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-268">By using the async feature, you can invoke asynchronous methods without using explicit callbacks or manually splitting your code across multiple methods or lambda expressions.</span></span>

<span data-ttu-id="9dcd3-269">메서드에 [async](language-reference/keywords/async.md) 한정자를 표시하면 메서드에서 [await](language-reference/operators/await.md) 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-269">If you mark a method with the [async](language-reference/keywords/async.md) modifier, you can use the [await](language-reference/operators/await.md) operator in the method.</span></span> <span data-ttu-id="9dcd3-270">제어가 비동기 메서드의 `await` 식에 도달하면 대기된 작업이 완료되지 않은 경우 제어가 호출자로 반환되고, 대기된 작업이 완료될 때까지 `await` 키워드가 있는 메서드의 진행이 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-270">When control reaches an `await` expression in the async method, control returns to the caller if the awaited task is not completed, and progress in the method with the `await` keyword is suspended until the awaited task completes.</span></span> <span data-ttu-id="9dcd3-271">작업이 완료되면 메서드가 실행이 다시 시작될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-271">When the task is complete, execution can resume in the method.</span></span>

> [!NOTE]
> <span data-ttu-id="9dcd3-272">비동기 메서드는 아직 완료되지 않은 첫 번째 대기된 개체를 검색할 때나 비동기 메서드의 끝에 도달할 때 중에서 먼저 발생하는 시점에 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-272">An async method returns to the caller when either it encounters the first awaited object that's not yet complete or it gets to the end of the async method, whichever occurs first.</span></span>

<span data-ttu-id="9dcd3-273">비동기 메서드는 일반적으로 반환 형식이 <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, <xref:System.Collections.Generic.IAsyncEnumerable%601> 또는 `void`입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-273">An async method typically has a return type of <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, <xref:System.Collections.Generic.IAsyncEnumerable%601>or `void`.</span></span> <span data-ttu-id="9dcd3-274">`void` 반환 형식은 기본적으로 `void` 반환 형식이 필요할 때 이벤트 처리기를 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-274">The `void` return type is used primarily to define event handlers, where a `void` return type is required.</span></span> <span data-ttu-id="9dcd3-275">`void`를 반환하는 비동기 메서드는 대기할 수 없고 void를 반환하는 메서드의 호출자는 메서드가 throw하는 예외를 catch할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-275">An async method that returns `void` can't be awaited, and the caller of a void-returning method can't catch exceptions that the method throws.</span></span> <span data-ttu-id="9dcd3-276">C# 7.0부터 비동기 메서드에는 [작업과 유사한 반환 형식](./whats-new/csharp-7.md#generalized-async-return-types)이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-276">Starting with C# 7.0, an async method can have [any task-like return type](./whats-new/csharp-7.md#generalized-async-return-types).</span></span>

<span data-ttu-id="9dcd3-277">다음 예제에서 `DelayAsync`는 정수를 반환하는 return 문을 포함하는 비동기 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-277">In the following example, `DelayAsync` is an async method that has a return statement that returns an integer.</span></span> <span data-ttu-id="9dcd3-278">비동기 메서드이기 때문에 해당 메서드 선언의 반환 형식은 `Task<int>`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-278">Because it is an async method, its method declaration must have a return type of `Task<int>`.</span></span> <span data-ttu-id="9dcd3-279">반환 형식이 `Task<int>`이므로 `DoSomethingAsync`의 `await` 식 계산에서 다음 `int result = await delayTask` 문과 같이 정수가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-279">Because the return type is `Task<int>`, the evaluation of the `await` expression in `DoSomethingAsync` produces an integer, as the following `int result = await delayTask` statement demonstrates.</span></span>

:::code language="csharp" source="programming-guide/classes-and-structs/snippets/classes-and-structs/methods/Program.cs":::

<span data-ttu-id="9dcd3-280">비동기 메서드는 모든 [in](language-reference/keywords/in-parameter-modifier.md), [ref](language-reference/keywords/ref.md) 또는 [out](language-reference/keywords/out-parameter-modifier.md) 매개 변수를 선언할 수 없지만, 이러한 매개 변수가 있는 메서드를 호출할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-280">An async method can't declare any [in](language-reference/keywords/in-parameter-modifier.md), [ref](language-reference/keywords/ref.md), or [out](language-reference/keywords/out-parameter-modifier.md) parameters, but it can call methods that have such parameters.</span></span>

 <span data-ttu-id="9dcd3-281">비동기 메서드에 관한 자세한 내용은 [async 및 await를 사용한 비동기 프로그래밍](async.md) 및 [비동기 반환 형식](programming-guide/concepts/async/async-return-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-281">For more information about async methods, see [Asynchronous programming with async and await](async.md) and [Async return types](programming-guide/concepts/async/async-return-types.md).</span></span>

<a name="expr"></a>

## <a name="expression-bodied-members"></a><span data-ttu-id="9dcd3-282">식 본문 멤버</span><span class="sxs-lookup"><span data-stu-id="9dcd3-282">Expression-bodied members</span></span>

<span data-ttu-id="9dcd3-283">일반적으로 식의 결과와 함께 바로 반환되거나 단일 문이 메서드 본문으로 포함된 메서드 정의가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-283">It is common to have method definitions that simply return immediately with the result of an expression, or that have a single statement as the body of the method.</span></span>  <span data-ttu-id="9dcd3-284">`=>`를 사용하여 해당 메서드를 속성을 정의하기 위한 구문 바로 가기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-284">There is a syntax shortcut for defining such methods using `=>`:</span></span>

```csharp
public Point Move(int dx, int dy) => new Point(x + dx, y + dy);
public void Print() => Console.WriteLine(First + " " + Last);
// Works with operators, properties, and indexers too.
public static Complex operator +(Complex a, Complex b) => a.Add(b);
public string Name => First + " " + Last;
public Customer this[long id] => store.LookupCustomer(id);
```

<span data-ttu-id="9dcd3-285">메서드가 `void`를 반환하거나 비동기 메서드이면 메서드 본문은 문 식이어야 합니다(람다에서와 같음).</span><span class="sxs-lookup"><span data-stu-id="9dcd3-285">If the method returns `void` or is an async method, the body of the method must be a statement expression (same as with lambdas).</span></span>  <span data-ttu-id="9dcd3-286">속성 및 인덱서의 경우 읽기 전용이어야 하며, `get` 접근자 키워드를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-286">For properties and indexers, they must be read-only, and you do not use the `get` accessor keyword.</span></span>

<a name="iterators"></a>

## <a name="iterators"></a><span data-ttu-id="9dcd3-287">Iterators</span><span class="sxs-lookup"><span data-stu-id="9dcd3-287">Iterators</span></span>

<span data-ttu-id="9dcd3-288">반복기는 배열 목록과 같은 컬렉션에 대해 사용자 지정 반복을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-288">An iterator performs a custom iteration over a collection, such as a list or an array.</span></span> <span data-ttu-id="9dcd3-289">반복기는 [yield return](language-reference/keywords/yield.md) 문을 사용하여 각 요소를 따로따로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-289">An iterator uses the [yield return](language-reference/keywords/yield.md) statement to return each element one at a time.</span></span> <span data-ttu-id="9dcd3-290">`yield return` 문에 도달하면 호출자가 시퀀스의 다음 요소를 요청할 수 있도록 현재 위치가 기억됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-290">When a `yield return` statement is reached, the current location is remembered so that the caller can request the next element in the sequence.</span></span>

<span data-ttu-id="9dcd3-291">반복기의 반환 형식은 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> 또는 <xref:System.Collections.Generic.IEnumerator%601>일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-291">The return type of an iterator can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="9dcd3-292">자세한 내용은 [반복기](programming-guide/concepts/iterators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-292">For more information, see [Iterators](programming-guide/concepts/iterators.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9dcd3-293">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9dcd3-293">See also</span></span>

- [<span data-ttu-id="9dcd3-294">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="9dcd3-294">Access Modifiers</span></span>](language-reference/keywords/access-modifiers.md)
- [<span data-ttu-id="9dcd3-295">정적 클래스 및 정적 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="9dcd3-295">Static Classes and Static Class Members</span></span>](programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [<span data-ttu-id="9dcd3-296">상속</span><span class="sxs-lookup"><span data-stu-id="9dcd3-296">Inheritance</span></span>](programming-guide/classes-and-structs/inheritance.md)
- [<span data-ttu-id="9dcd3-297">추상/봉인된 클래스 및 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="9dcd3-297">Abstract and Sealed Classes and Class Members</span></span>](programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)
- [<span data-ttu-id="9dcd3-298">params</span><span class="sxs-lookup"><span data-stu-id="9dcd3-298">params</span></span>](language-reference/keywords/params.md)
- [<span data-ttu-id="9dcd3-299">out</span><span class="sxs-lookup"><span data-stu-id="9dcd3-299">out</span></span>](language-reference/keywords/out-parameter-modifier.md)
- [<span data-ttu-id="9dcd3-300">ref</span><span class="sxs-lookup"><span data-stu-id="9dcd3-300">ref</span></span>](language-reference/keywords/ref.md)
- [<span data-ttu-id="9dcd3-301">in</span><span class="sxs-lookup"><span data-stu-id="9dcd3-301">in</span></span>](language-reference/keywords/in-parameter-modifier.md)
- [<span data-ttu-id="9dcd3-302">매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="9dcd3-302">Passing Parameters</span></span>](programming-guide/classes-and-structs/passing-parameters.md)
