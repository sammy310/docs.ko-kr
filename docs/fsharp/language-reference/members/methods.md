---
title: 메서드
description: F# 메서드가 개체 및 형식의 기능 및 동작을 노출하고 구현하는 데 사용되는 형식과 연결된 함수인 방법을 알아봅니다.
ms.date: 11/04/2019
ms.openlocfilehash: 6f5ae76ea450b07763eb58d0c95b18b30f634551
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401066"
---
# <a name="methods"></a><span data-ttu-id="18c63-103">메서드</span><span class="sxs-lookup"><span data-stu-id="18c63-103">Methods</span></span>

<span data-ttu-id="18c63-104">*메서드는* 형식과 연결된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-104">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="18c63-105">개체 지향 프로그래밍에서는 메서드를 사용하여 개체 및 형식의 기능 및 동작을 노출하고 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-105">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>

## <a name="syntax"></a><span data-ttu-id="18c63-106">구문</span><span class="sxs-lookup"><span data-stu-id="18c63-106">Syntax</span></span>

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-name parameter-list [ : return-type ] =
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member method-name : type-signature
[ attributes ]
default self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue( default-value )>] input) [ : return-type ]
```

## <a name="remarks"></a><span data-ttu-id="18c63-107">설명</span><span class="sxs-lookup"><span data-stu-id="18c63-107">Remarks</span></span>

<span data-ttu-id="18c63-108">이전 구문에서 다양한 형태의 메서드 선언 및 정의를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-108">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="18c63-109">더 긴 메서드 바디에서 줄 바이탈은 등가부(=)를 따르고 전체 메서드 본문이 들여쓰기됩니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-109">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="18c63-110">특성은 모든 메서드 선언에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-110">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="18c63-111">메서드 정의에 대 한 구문 앞에 표시 되며 일반적으로 별도 줄에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-111">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="18c63-112">자세한 내용은 [특성](../attributes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18c63-112">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="18c63-113">메서드를 표시할 `inline`수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-113">Methods can be marked `inline`.</span></span> <span data-ttu-id="18c63-114">`inline`에 대한 내용은 [인라인 함수](../functions/inline-functions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18c63-114">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="18c63-115">비인라인 메서드는 형식 내에서 재귀적으로 사용할 수 있습니다. `rec` 키워드를 명시적으로 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-115">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>

## <a name="instance-methods"></a><span data-ttu-id="18c63-116">인스턴스 방법</span><span class="sxs-lookup"><span data-stu-id="18c63-116">Instance Methods</span></span>

<span data-ttu-id="18c63-117">인스턴스 메서드는 `member` 키워드와 자체 *식별자로*선언되고 마침표(.) 및 메서드 이름 및 매개 변수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-117">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="18c63-118">바인딩의 경우와 마찬가지로 *매개 변수 목록은* 패턴일 수 있습니다. `let`</span><span class="sxs-lookup"><span data-stu-id="18c63-118">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="18c63-119">일반적으로 메서드 매개 변수를 튜플 형식으로 괄호안에 포함하면 메서드가 다른 .NET Framework 언어로 만들 때 F#에 표시되는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-119">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="18c63-120">그러나 커리 형식(공백으로 구분된 매개 변수)도 일반적이며 다른 패턴도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-120">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="18c63-121">다음 예제에서는 비추상 인스턴스 메서드의 정의 및 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-121">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="18c63-122">인스턴스 메서드 내에서 let 바인딩을 사용 하 여 정의 된 필드에 액세스 하는 자체 식별자를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="18c63-122">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="18c63-123">다른 멤버 및 속성에 액세스할 때 자체 식별자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-123">Use the self identifier when accessing other members and properties.</span></span>

## <a name="static-methods"></a><span data-ttu-id="18c63-124">정적 메서드</span><span class="sxs-lookup"><span data-stu-id="18c63-124">Static Methods</span></span>

<span data-ttu-id="18c63-125">키워드는 `static` 메서드가 인스턴스 없이 호출될 수 있고 개체 인스턴스와 연결되지 않도록 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-125">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="18c63-126">그렇지 않으면 메서드는 인스턴스 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-126">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="18c63-127">다음 섹션의 예제에서는 `let` 키워드로 선언된 필드, `member` 키워드로 선언된 속성 멤버 및 `static` 키워드로 선언된 정적 메서드를 보여 주십습니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-127">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="18c63-128">다음 예제에서는 정적 메서드의 정의 및 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-128">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="18c63-129">이러한 메서드 정의가 이전 `SomeType` 섹션의 클래스에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-129">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="18c63-130">추상 메서드 및 가상 메서드</span><span class="sxs-lookup"><span data-stu-id="18c63-130">Abstract and Virtual Methods</span></span>

<span data-ttu-id="18c63-131">키워드는 `abstract` 메서드에 가상 디스패치 슬롯이 있으며 클래스에 정의가 없을 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-131">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="18c63-132">*가상 디스패치 슬롯은* 런타임에 개체 지향 형식의 가상 함수 호출을 조회하는 데 사용되는 내부적으로 유지 관리되는 함수 테이블의 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-132">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="18c63-133">가상 디스패치 메커니즘은 개체 지향 프로그래밍의 중요한 기능인 *다형성을*구현하는 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-133">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="18c63-134">정의없이 하나 이상의 추상 메서드가있는 클래스는 *추상 클래스이며,* 이는 해당 클래스의 인스턴스를 만들 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-134">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="18c63-135">추상 클래스에 대한 자세한 내용은 [추상 클래스를](../abstract-classes.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="18c63-135">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="18c63-136">추상 메서드 선언에는 메서드 본문이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-136">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="18c63-137">대신 메서드 의 이름 뒤에 콜론(:)이 표시됩니다. 및 메서드에 대한 형식 시그니처입니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-137">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="18c63-138">메서드의 형식 시그니처는 매개 변수 이름이 없는 경우를 제외하고 Visual Studio 코드 편집기의 메서드 이름 위에 마우스 포인터를 일시 중지할 때 IntelliSense에서 표시한 것과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-138">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="18c63-139">대화식으로 작업할 때 인터프리터 fsi.exe에서도 형식 서명이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-139">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="18c63-140">메서드의 형식 시그니처는 매개 변수의 형식을 나열하고 적절한 구분 기호를 사용하여 반환 형식을 나열하여 형성됩니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-140">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="18c63-141">커리 매개변수는 로 `->` 구분되고 튜플 매개변수는 `*`에 의해 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-141">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="18c63-142">반환 값은 항상 `->` 기호로 인수와 분리됩니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-142">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="18c63-143">괄호는 함수 형식이 매개 변수인 경우와 같은 복잡한 매개 변수를 그룹화하거나 튜플이 두 매개 변수가 아닌 단일 매개변수로 처리되는 시기를 나타내는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-143">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="18c63-144">이 항목의 구문 블록에 표시된 대로 클래스에 정의를 `default` 추가하고 키워드를 사용하여 추상 메서드 기본 정의를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-144">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="18c63-145">동일한 클래스에 정의가 있는 추상 메서드는 다른 .NET Framework 언어의 가상 메서드와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-145">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="18c63-146">정의가 있는지 여부에 관계없이 `abstract` 키워드는 클래스의 가상 함수 테이블에 새 디스패치 슬롯을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-146">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="18c63-147">기본 클래스가 추상 메서드를 구현하는지 여부에 관계없이 파생 클래스는 추상 메서드의 구현을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-147">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="18c63-148">파생 클래스에서 추상 메서드를 구현하려면 또는 `override` `default` 키워드를 사용하지 말고 파생 클래스에 동일한 이름과 서명을 가지는 메서드를 정의하고 메서드 본문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-148">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="18c63-149">키워드와 `override` `default` 정확히 같은 것을 의미한다.</span><span class="sxs-lookup"><span data-stu-id="18c63-149">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="18c63-150">새 `override` 메서드가 기본 클래스 구현을 재정의하는 경우 사용합니다. 원래 `default` 추상 선언과 동일한 클래스에서 구현을 만들 때 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-150">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="18c63-151">기본 클래스에서 `abstract` 추상으로 선언된 메서드를 구현하는 메서드에서 키워드를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="18c63-151">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="18c63-152">다음 예제에서는 .NET `Rotate` Framework 가상 메서드와 동일한 기본 구현이 있는 추상 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-152">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="18c63-153">다음 예제에서는 기본 클래스 메서드를 재정의하는 파생 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-153">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="18c63-154">이 경우 재정의는 메서드가 아무 것도 수행하지 않도록 동작을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-154">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="18c63-155">오버로드된 메서드</span><span class="sxs-lookup"><span data-stu-id="18c63-155">Overloaded Methods</span></span>

<span data-ttu-id="18c63-156">오버로드된 메서드는 지정된 형식에 이름이 동일하지만 인수가 다른 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-156">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="18c63-157">F#에서 선택적 인수는 일반적으로 오버로드된 메서드 대신 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-157">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="18c63-158">그러나 인수가 커리 형식이 아닌 튜플 형식인 경우 오버로드된 메서드는 언어에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-158">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="18c63-159">선택적 인수</span><span class="sxs-lookup"><span data-stu-id="18c63-159">Optional Arguments</span></span>

<span data-ttu-id="18c63-160">F # 4.1로 시작하여 메서드에서 기본 매개 변수 값이있는 선택적 인수를 가질 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-160">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="18c63-161">이는 C# 코드와의 상호 운용을 용이하게 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-161">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="18c63-162">다음 예제에서는 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-162">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    _.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="18c63-163">에 `DefaultParameterValue` 전달 된 값은 입력 형식과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-163">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="18c63-164">위의 샘플에서, 그것은 `int`이다.</span><span class="sxs-lookup"><span data-stu-id="18c63-164">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="18c63-165">정수가 아닌 값을 `DefaultParameterValue` 전달하려고 하면 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-165">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="18c63-166">예: 속성 및 메서드</span><span class="sxs-lookup"><span data-stu-id="18c63-166">Example: Properties and Methods</span></span>

<span data-ttu-id="18c63-167">다음 예제에는 필드, 개인 함수, 속성 및 정적 메서드의 예가 있는 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18c63-167">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="18c63-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18c63-168">See also</span></span>

- [<span data-ttu-id="18c63-169">멤버</span><span class="sxs-lookup"><span data-stu-id="18c63-169">Members</span></span>](index.md)
