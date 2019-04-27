---
title: 클래스
description: 설명 하는 방법 F# 클래스는 속성, 메서드 및 이벤트를 가질 수 있는 개체를 나타내는 형식입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 6bf838e98acecb89436d3e87809d9eb6da0c66d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61870294"
---
# <a name="classes"></a><span data-ttu-id="257f5-103">클래스</span><span class="sxs-lookup"><span data-stu-id="257f5-103">Classes</span></span>

<span data-ttu-id="257f5-104">*클래스* 는 속성, 메서드 및 이벤트를 보유할 수 있는 개체를 나타내는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-104">*Classes* are types that represent objects that can have properties, methods, and events.</span></span>

## <a name="syntax"></a><span data-ttu-id="257f5-105">구문</span><span class="sxs-lookup"><span data-stu-id="257f5-105">Syntax</span></span>

```fsharp
// Class definition:
type [access-modifier] type-name [type-params] [access-modifier] ( parameter-list ) [ as identifier ] =
[ class ]
[ inherit base-type-name(base-constructor-args) ]
[ let-bindings ]
[ do-bindings ]
member-list
...
[ end ]
// Mutually recursive class definitions:
type [access-modifier] type-name1 ...
and [access-modifier] type-name2 ...
...
```

## <a name="remarks"></a><span data-ttu-id="257f5-106">설명</span><span class="sxs-lookup"><span data-stu-id="257f5-106">Remarks</span></span>

<span data-ttu-id="257f5-107">클래스에 대 한.NET 개체 형식; 기본 설명을 나타내는합니다 클래스의 개체 지향 프로그래밍을 지 원하는 기본 형식 개념은 F#입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-107">Classes represent the fundamental description of .NET object types; the class is the primary type concept that supports object-oriented programming in F#.</span></span>

<span data-ttu-id="257f5-108">위의 구문에서은 `type-name` 은 임의의 유효한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-108">In the preceding syntax, the `type-name` is any valid identifier.</span></span> <span data-ttu-id="257f5-109">`type-params` 선택적 제네릭 형식 매개 변수를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-109">The `type-params` describes optional generic type parameters.</span></span> <span data-ttu-id="257f5-110">형식 매개 변수 이름과 꺾쇠 괄호로 묶여 있는 제약 조건을 구성 됩니다 (`<` 고 `>`).</span><span class="sxs-lookup"><span data-stu-id="257f5-110">It consists of type parameter names and constraints enclosed in angle brackets (`<` and `>`).</span></span> <span data-ttu-id="257f5-111">자세한 내용은 [제네릭](generics/index.md) 하 고 [제약 조건](generics/constraints.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-111">For more information, see [Generics](generics/index.md) and [Constraints](generics/constraints.md).</span></span> <span data-ttu-id="257f5-112">`parameter-list` 생성자 매개 변수를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-112">The `parameter-list` describes constructor parameters.</span></span> <span data-ttu-id="257f5-113">형식에 관련 된 첫 번째 액세스 한정자 두 번째 기본 생성자와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-113">The first access modifier pertains to the type; the second pertains to the primary constructor.</span></span> <span data-ttu-id="257f5-114">두 경우 모두 기본값은 `public`합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-114">In both cases, the default is `public`.</span></span>

<span data-ttu-id="257f5-115">사용 하 여 클래스에 대 한 기본 클래스를 지정 하는 `inherit` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-115">You specify the base class for a class by using the `inherit` keyword.</span></span> <span data-ttu-id="257f5-116">괄호의 기본 클래스 생성자에 대 한 인수를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-116">You must supply arguments, in parentheses, for the base class constructor.</span></span>

<span data-ttu-id="257f5-117">필드를 선언 하거나 함수를 사용 하 여 로컬 클래스에 있는 값 `let` 바인딩 및 수에 대 한 일반 규칙을 따라야 `let` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="257f5-117">You declare fields or function values that are local to the class by using `let` bindings, and you must follow the general rules for `let` bindings.</span></span> <span data-ttu-id="257f5-118">`do-bindings` 섹션 개체 생성 시 실행할 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-118">The `do-bindings` section includes code to be executed upon object construction.</span></span>

<span data-ttu-id="257f5-119">`member-list` 추가 생성자, 인스턴스 및 정적 메서드 선언, 인터페이스 선언에서 추상 바인딩 및 속성 및 이벤트 선언으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-119">The `member-list` consists of additional constructors, instance and static method declarations, interface declarations, abstract bindings, and property and event declarations.</span></span> <span data-ttu-id="257f5-120">에 설명 된 이러한 [멤버](members/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-120">These are described in [Members](members/index.md).</span></span>

<span data-ttu-id="257f5-121">합니다 `identifier` 선택적으로 사용 되는 `as` 키워드 인스턴스 변수 또는 형식의 인스턴스를 참조 하도록 형식 정의에 사용할 수 있는 자체 식별자 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-121">The `identifier` that is used with the optional `as` keyword gives a name to the instance variable, or self identifier, which can be used in the type definition to refer to the instance of the type.</span></span> <span data-ttu-id="257f5-122">자세한 내용은이 항목 뒷부분의 자체 식별자 섹션을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-122">For more information, see the section Self Identifiers later in this topic.</span></span>

<span data-ttu-id="257f5-123">키워드 `class` 고 `end` 시작을 표시 하 고 정의의 끝은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-123">The keywords `class` and `end` that mark the start and end of the definition are optional.</span></span>

<span data-ttu-id="257f5-124">서로 참조 하는 형식에는 재귀 형식 함께 조인 되는 함께 사용할 수는 `and` 상호 재귀 함수는 마찬가지로 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-124">Mutually recursive types, which are types that reference each other, are joined together with the `and` keyword just as mutually recursive functions are.</span></span> <span data-ttu-id="257f5-125">예를 들어 상호 재귀 형식 섹션을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-125">For an example, see the section Mutually Recursive Types.</span></span>

## <a name="constructors"></a><span data-ttu-id="257f5-126">생성자</span><span class="sxs-lookup"><span data-stu-id="257f5-126">Constructors</span></span>

<span data-ttu-id="257f5-127">생성자는 클래스 형식의 인스턴스를 만드는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-127">The constructor is code that creates an instance of the class type.</span></span> <span data-ttu-id="257f5-128">클래스에 대 한 생성자에서와 다르게 작동 F# 다른.NET 언어에서 수행한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-128">Constructors for classes work somewhat differently in F# than they do in other .NET languages.</span></span> <span data-ttu-id="257f5-129">에 F# 클래스, 해당 인수에 설명 된 기본 생성자는 항상 합니다 `parameter-list` 오는 형식 이름 및 해당 본문으로 구성 됩니다는 `let` (및 `let rec`) 바인딩 클래스 선언의 시작 및 `do` 뒤에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-129">In an F# class, there is always a primary constructor whose arguments are described in the `parameter-list` that follows the type name, and whose body consists of the `let` (and `let rec`) bindings at the start of the class declaration and the `do` bindings that follow.</span></span> <span data-ttu-id="257f5-130">기본 생성자의 인수는 클래스 선언 전체 범위에.</span><span class="sxs-lookup"><span data-stu-id="257f5-130">The arguments of the primary constructor are in scope throughout the class declaration.</span></span>

<span data-ttu-id="257f5-131">추가 생성자를 사용 하 여 추가할 수 있습니다는 `new` 키워드를 다음과 같이 멤버를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-131">You can add additional constructors by using the `new` keyword to add a member, as follows:</span></span>

<span data-ttu-id="257f5-132">`new`(`argument-list`) = `constructor-body`</span><span class="sxs-lookup"><span data-stu-id="257f5-132">`new`(`argument-list`) = `constructor-body`</span></span>

<span data-ttu-id="257f5-133">새로운 생성자의 본문 클래스 선언의 맨 위에 있는 지정 된 기본 생성자를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-133">The body of the new constructor must invoke the primary constructor that is specified at the top of the class declaration.</span></span>

<span data-ttu-id="257f5-134">다음 예제에서는이 개념을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-134">The following example illustrates this concept.</span></span> <span data-ttu-id="257f5-135">다음 코드에서 `MyClass` 두 생성자에는 두 개의 인수 및 다른 생성자는 기본 생성자에 인수가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-135">In the following code, `MyClass` has two constructors, a primary constructor that takes two arguments and another constructor that takes no arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]

## <a name="let-and-do-bindings"></a><span data-ttu-id="257f5-136">let 및 do 바인딩</span><span class="sxs-lookup"><span data-stu-id="257f5-136">let and do Bindings</span></span>

<span data-ttu-id="257f5-137">합니다 `let` 및 `do` 클래스 정의에서 바인딩을 기본 클래스 생성자의 본문을 형성 하 고 실행 되므로 클래스 인스턴스를 만들 때마다 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-137">The `let` and `do` bindings in a class definition form the body of the primary class constructor, and therefore they run whenever a class instance is created.</span></span> <span data-ttu-id="257f5-138">경우는 `let` 바인딩 함수는 다음 멤버는 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-138">If a `let` binding is a function, then it is compiled into a member.</span></span> <span data-ttu-id="257f5-139">경우는 `let` 바인딩 함수 또는 멤버에서 사용 되지 않는 값을 생성자에 로컬인 변수는 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-139">If the `let` binding is a value that is not used in any function or member, then it is compiled into a variable that is local to the constructor.</span></span> <span data-ttu-id="257f5-140">그렇지 않으면 클래스의 필드로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-140">Otherwise, it is compiled into a field of the class.</span></span> <span data-ttu-id="257f5-141">`do` 식 다음에 나오는 기본 생성자로 컴파일되고 모든 인스턴스에 대 한 초기화 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-141">The `do` expressions that follow are compiled into the primary constructor and execute initialization code for every instance.</span></span> <span data-ttu-id="257f5-142">추가 생성자에는 항상 기본 생성자를 호출 하므로 합니다 `let` 바인딩 및 `do` 바인딩은 생성자가 호출에 관계 없이 항상 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-142">Because any additional constructors always call the primary constructor, the `let` bindings and `do` bindings always execute regardless of which constructor is called.</span></span>

<span data-ttu-id="257f5-143">그러나 만든 필드 `let` 액세스할 수에서 정적 메서드는 정적 메서드를 매개 변수로 인스턴스 변수를 사용 하는 경우에; 바인딩 메서드 및 클래스의 속성을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-143">Fields that are created by `let` bindings can be accessed throughout the methods and properties of the class; however, they cannot be accessed from static methods, even if the static methods take an instance variable as a parameter.</span></span> <span data-ttu-id="257f5-144">이러한 있을 경우, 자체 식별자를 사용 하 여 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-144">They cannot be accessed by using the self identifier, if one exists.</span></span>

## <a name="self-identifiers"></a><span data-ttu-id="257f5-145">자체 식별자</span><span class="sxs-lookup"><span data-stu-id="257f5-145">Self Identifiers</span></span>

<span data-ttu-id="257f5-146">A *자체 식별자* 현재 인스턴스를 나타내는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-146">A *self identifier* is a name that represents the current instance.</span></span> <span data-ttu-id="257f5-147">자체 식별자와 유사 합니다 `this` 키워드 C# 또는 C++ 또는 `Me` Visual Basic의 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-147">Self identifiers resemble the `this` keyword in C# or C++ or `Me` in Visual Basic.</span></span> <span data-ttu-id="257f5-148">전체 클래스 정의 대 한 또는 개별 메서드에 대해서만 범위 내에서에 자체 식별자 여부에 따라 두 가지 방법으로 자체 식별자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-148">You can define a self identifier in two different ways, depending on whether you want the self identifier to be in scope for the whole class definition or just for an individual method.</span></span>

<span data-ttu-id="257f5-149">전체 클래스에 대 한 자체 식별자를 정의 하려면 사용 된 `as` 생성자 매개 변수의 닫는 괄호 뒤 키워드 목록 및 식별자 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-149">To define a self identifier for the whole class, use the `as` keyword after the closing parentheses of the constructor parameter list, and specify the identifier name.</span></span>

<span data-ttu-id="257f5-150">단 하나의 메서드에 대 한 자체 식별자를 정의 하는 메서드 이름과 구분 기호로 마침표 (.) 직전 멤버 선언에서 자체 식별자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-150">To define a self identifier for just one method, provide the self identifier in the member declaration, just before the method name and a period (.) as a separator.</span></span>

<span data-ttu-id="257f5-151">다음 코드 예제에는 자체 식별자는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-151">The following code example illustrates the two ways to create a self identifier.</span></span> <span data-ttu-id="257f5-152">첫 번째 줄에서은 `as` 키워드 자체 식별자를 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-152">In the first line, the `as` keyword is used to define the self identifier.</span></span> <span data-ttu-id="257f5-153">다섯 번째 줄에서는 식별자 `this` 범위가 메서드로 제한 된 자체 식별자를 정의 하는 데 사용 됩니다 `PrintMessage`합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-153">In the fifth line, the identifier `this` is used to define a self identifier whose scope is restricted to the method `PrintMessage`.</span></span>

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

<span data-ttu-id="257f5-154">와 달리 다른.NET 언어의 이름을 지정할 수 있습니다 자체 식별자 원하는; 수에 제한 되지 않습니다 이름은 같은 `self`, `Me`, 또는 `this`합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-154">Unlike in other .NET languages, you can name the self identifier however you want; you are not restricted to names such as `self`, `Me`, or `this`.</span></span>

<span data-ttu-id="257f5-155">선언 된 자체 식별자를 `as` 키워드 될 때까지 초기화 되지 않은 후는 `let` 바인딩이 실행 되 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-155">The self identifier that is declared with the `as` keyword is not initialized until after the `let` bindings are executed.</span></span> <span data-ttu-id="257f5-156">따라서에서 사용할 수는 `let` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="257f5-156">Therefore, it cannot be used in the `let` bindings.</span></span> <span data-ttu-id="257f5-157">자체 식별자를 사용할 수는 `do` 바인딩 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-157">You can use the self identifier in the `do` bindings section.</span></span>

## <a name="generic-type-parameters"></a><span data-ttu-id="257f5-158">제네릭 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="257f5-158">Generic Type Parameters</span></span>

<span data-ttu-id="257f5-159">제네릭 형식 매개 변수를 꺾쇠 괄호로 지정 됩니다 (`<` 및 `>`), 작은 따옴표 뒤에 식별자의 형태로 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-159">Generic type parameters are specified in angle brackets (`<` and `>`), in the form of a single quotation mark followed by an identifier.</span></span> <span data-ttu-id="257f5-160">여러 제네릭 형식 매개 변수는 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-160">Multiple generic type parameters are separated by commas.</span></span> <span data-ttu-id="257f5-161">제네릭 형식 매개 변수는 선언 전체 범위의 경우</span><span class="sxs-lookup"><span data-stu-id="257f5-161">The generic type parameter is in scope throughout the declaration.</span></span> <span data-ttu-id="257f5-162">다음 코드 예제에서는 제네릭 형식 매개 변수를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-162">The following code example shows how to specify generic type parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

<span data-ttu-id="257f5-163">형식 인수 형식을 사용 하는 경우 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-163">Type arguments are inferred when the type is used.</span></span> <span data-ttu-id="257f5-164">다음 코드에서는 유추 된 형식은 튜플 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-164">In the following code, the inferred type is a sequence of tuples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]

## <a name="specifying-inheritance"></a><span data-ttu-id="257f5-165">상속을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-165">Specifying Inheritance</span></span>

<span data-ttu-id="257f5-166">`inherit` 있을 경우 절은 직접 기본 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-166">The `inherit` clause identifies the direct base class, if there is one.</span></span> <span data-ttu-id="257f5-167">F#, 하나의 직접 기본 클래스는 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-167">In F#, only one direct base class is allowed.</span></span> <span data-ttu-id="257f5-168">클래스가 구현 하는 인터페이스는 기본 클래스를 고려 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-168">Interfaces that a class implements are not considered base classes.</span></span> <span data-ttu-id="257f5-169">인터페이스에 설명 되어는 [인터페이스](Interfaces.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-169">Interfaces are discussed in the [Interfaces](Interfaces.md) topic.</span></span>

<span data-ttu-id="257f5-170">있습니다 수는 메서드 및 속성 액세스 기본 클래스의 파생된 클래스에서 언어 키워드를 사용 하 여 `base` 는 식별자 뒤에 마침표 (.) 및 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-170">You can access the methods and properties of the base class from the derived class by using the language keyword `base` as an identifier, followed by a period (.) and the name of the member.</span></span>

<span data-ttu-id="257f5-171">자세한 내용은 [상속](inheritance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="257f5-171">For more information, see [Inheritance](inheritance.md).</span></span>

## <a name="members-section"></a><span data-ttu-id="257f5-172">멤버 섹션</span><span class="sxs-lookup"><span data-stu-id="257f5-172">Members Section</span></span>

<span data-ttu-id="257f5-173">이 섹션의 정적 또는 인스턴스 메서드, 속성, 인터페이스 구현, 추상 멤버, 이벤트 선언 및 추가 생성자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-173">You can define static or instance methods, properties, interface implementations, abstract members, event declarations, and additional constructors in this section.</span></span> <span data-ttu-id="257f5-174">수 있도록 하 고 수행 바인딩을이 섹션에 나타날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-174">Let and do bindings cannot appear in this section.</span></span> <span data-ttu-id="257f5-175">다양 한 멤버를 추가할 수 있으므로 F# 형식 클래스 외에도 별도 항목에서 설명 [멤버](members/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-175">Because members can be added to a variety of F# types in addition to classes, they are discussed in a separate topic, [Members](members/index.md).</span></span>

## <a name="mutually-recursive-types"></a><span data-ttu-id="257f5-176">상호 재귀 형식</span><span class="sxs-lookup"><span data-stu-id="257f5-176">Mutually Recursive Types</span></span>

<span data-ttu-id="257f5-177">순환 방식으로 서로 참조 하는 형식을 정의할 때 있습니다 문자열 함께 형식 정의 사용 하 여는 `and` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-177">When you define types that reference each other in a circular way, you string together the type definitions by using the `and` keyword.</span></span> <span data-ttu-id="257f5-178">합니다 `and` 키워드를 대체 합니다 `type` 다음과 같이 첫 번째 정의 제외한 모든 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-178">The `and` keyword replaces the `type` keyword on all except the first definition, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

<span data-ttu-id="257f5-179">출력은 현재 디렉터리에 있는 모든 파일의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-179">The output is a list of all the files in the current directory.</span></span>

## <a name="when-to-use-classes-unions-records-and-structures"></a><span data-ttu-id="257f5-180">클래스, 공용 구조체, 레코드 및 구조를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="257f5-180">When to Use Classes, Unions, Records, and Structures</span></span>

<span data-ttu-id="257f5-181">다양 한 선택할 수 있는 형식이 지정 되 면 새로운 각 유형에 설계에 대 한 특정 상황에 대 한 적절 한 유형을 선택 하려면 잘 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-181">Given the variety of types to choose from, you need to have a good understanding of what each type is designed for to select the appropriate type for a particular situation.</span></span> <span data-ttu-id="257f5-182">클래스는 개체 지향 프로그래밍 컨텍스트에서 사용 하기 위해 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-182">Classes are designed for use in object-oriented programming contexts.</span></span> <span data-ttu-id="257f5-183">개체 지향 프로그래밍은.NET Framework에 대해 작성 된 응용 프로그램에서 사용 하는 기준 패러다임입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-183">Object-oriented programming is the dominant paradigm used in applications that are written for the .NET Framework.</span></span> <span data-ttu-id="257f5-184">경우에 F# .NET Framework 또는 다른 개체 지향 라이브러리와 밀접 하 게 작동 하는 코드 및 클래스는 아마도 적절 한 UI 라이브러리와 같은 개체 지향 형식 시스템을 확장 해야 하는 경우에 특히 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-184">If your F# code has to work closely with the .NET Framework or another object-oriented library, and especially if you have to extend from an object-oriented type system such as a UI library, classes are probably appropriate.</span></span>

<span data-ttu-id="257f5-185">하지 상호 작용 하는 긴밀 하 게 코드 개체 지향 또는 자체 포함 되어 있으므로 개체 지향 코드와 자주 상호 작용 으로부터 보호 하는 코드를 작성 하는 경우 레코드를 사용 하 여 고려해 야 하 고 구별 된 공용 구조체.</span><span class="sxs-lookup"><span data-stu-id="257f5-185">If you are not interoperating closely with object-oriented code, or if you are writing code that is self-contained and therefore protected from frequent interaction with object-oriented code, you should consider using records and discriminated unions.</span></span> <span data-ttu-id="257f5-186">단일도 생각 하 여 작성 한 적절 한 패턴 일치 코드와 함께 구별 된 공용 구조체 개체 계층 구조에는 보다 간단한 대안으로 자주 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-186">A single, well thought–out discriminated union, together with appropriate pattern matching code, can often be used as a simpler alternative to an object hierarchy.</span></span> <span data-ttu-id="257f5-187">구별 된 공용 구조체에 대 한 자세한 내용은 참조 하세요. [구별 된 공용 구조체](discriminated-unions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-187">For more information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

<span data-ttu-id="257f5-188">레코드 클래스를 보다 간단 하다는 이점이 없지만 단순성을 사용 하 여 수행할 수 있는 형식의 요구 초과 하는 경우 레코드 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-188">Records have the advantage of being simpler than classes, but records are not appropriate when the demands of a type exceed what can be accomplished with their simplicity.</span></span> <span data-ttu-id="257f5-189">레코드는 기본적으로 단순 집계 값을 사용자 지정 작업을 수행할 수 있는 별도 생성자가 없는, 숨겨진된 필드를 상속 하거나 인터페이스 구현 없이입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-189">Records are basically simple aggregates of values, without separate constructors that can perform custom actions, without hidden fields, and without inheritance or interface implementations.</span></span> <span data-ttu-id="257f5-190">더 복잡 한 동작을 확인 하는 레코드를 속성 및 메서드와 같은 멤버를 추가할 수 있지만 레코드에 저장 되는 필드는 여전히 값의 간단한 집계.</span><span class="sxs-lookup"><span data-stu-id="257f5-190">Although members such as properties and methods can be added to records to make their behavior more complex, the fields stored in a record are still a simple aggregate of values.</span></span> <span data-ttu-id="257f5-191">레코드에 대 한 자세한 내용은 참조 하세요. [레코드](records.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-191">For more information about records, see [Records](records.md).</span></span>

<span data-ttu-id="257f5-192">구조 데이터의 작은 집계에도 유용 하지만.NET의 값 형식에 클래스 및 레코드에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-192">Structures are also useful for small aggregates of data, but they differ from classes and records in that they are .NET value types.</span></span> <span data-ttu-id="257f5-193">클래스 및 레코드에는.NET 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-193">Classes and records are .NET reference types.</span></span> <span data-ttu-id="257f5-194">값 형식을 값으로 전달 되는 값 형식과 참조 의미 체계 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-194">The semantics of value types and reference types are different in that value types are passed by value.</span></span> <span data-ttu-id="257f5-195">즉, 복사 되는 비트 수준 매개 변수로 전달 하거나 함수에서 반환 하는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-195">This means that they are copied bit for bit when they are passed as a parameter or returned from a function.</span></span> <span data-ttu-id="257f5-196">또한 스택에 저장 인지, 대신 부모 개체 내에 포함 된 필드로 사용 하는 경우 힙의 고유한 별도 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-196">They are also stored on the stack or, if they are used as a field, embedded inside the parent object instead of stored in their own separate location on the heap.</span></span> <span data-ttu-id="257f5-197">따라서 힙에 액세스 하는 오버 헤드가 문제인 경우 구조는 자주 액세스 하는 데이터에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-197">Therefore, structures are appropriate for frequently accessed data when the overhead of accessing the heap is a problem.</span></span> <span data-ttu-id="257f5-198">구조에 대 한 자세한 내용은 참조 하세요. [구조](structures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="257f5-198">For more information about structures, see [Structures](structures.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="257f5-199">참고자료</span><span class="sxs-lookup"><span data-stu-id="257f5-199">See also</span></span>

- [<span data-ttu-id="257f5-200">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="257f5-200">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="257f5-201">멤버</span><span class="sxs-lookup"><span data-stu-id="257f5-201">Members</span></span>](members/index.md)
- [<span data-ttu-id="257f5-202">상속</span><span class="sxs-lookup"><span data-stu-id="257f5-202">Inheritance</span></span>](inheritance.md)
- [<span data-ttu-id="257f5-203">인터페이스</span><span class="sxs-lookup"><span data-stu-id="257f5-203">Interfaces</span></span>](interfaces.md)