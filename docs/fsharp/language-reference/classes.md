---
title: 클래스
description: 'F # 클래스가 속성, 메서드 및 이벤트를 포함할 수 있는 개체를 나타내는 형식에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: fd6638e0f1c08cf667a73582e19b2bb5bba46e20
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970169"
---
# <a name="classes"></a><span data-ttu-id="40d6b-103">클래스</span><span class="sxs-lookup"><span data-stu-id="40d6b-103">Classes</span></span>

<span data-ttu-id="40d6b-104">*클래스* 는 속성, 메서드 및 이벤트를 포함할 수 있는 개체를 나타내는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-104">*Classes* are types that represent objects that can have properties, methods, and events.</span></span>

## <a name="syntax"></a><span data-ttu-id="40d6b-105">구문</span><span class="sxs-lookup"><span data-stu-id="40d6b-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="40d6b-106">설명</span><span class="sxs-lookup"><span data-stu-id="40d6b-106">Remarks</span></span>

<span data-ttu-id="40d6b-107">클래스는 .NET 개체 형식에 대 한 기본 설명을 나타냅니다. 클래스는 F #의 개체 지향 프로그래밍을 지 원하는 기본 형식 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-107">Classes represent the fundamental description of .NET object types; the class is the primary type concept that supports object-oriented programming in F#.</span></span>

<span data-ttu-id="40d6b-108">위의 구문에서는 `type-name` 유효한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-108">In the preceding syntax, the `type-name` is any valid identifier.</span></span> <span data-ttu-id="40d6b-109">는 `type-params` 선택적 제네릭 형식 매개 변수를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-109">The `type-params` describes optional generic type parameters.</span></span> <span data-ttu-id="40d6b-110">이 매개 변수는 형식 매개 변수 이름과 꺾쇠 괄호 (및)로 묶은 제약 조건으로 구성 됩니다 `<` `>` .</span><span class="sxs-lookup"><span data-stu-id="40d6b-110">It consists of type parameter names and constraints enclosed in angle brackets (`<` and `>`).</span></span> <span data-ttu-id="40d6b-111">자세한 내용은 [제네릭](./generics/index.md) 및 [제약 조건](./generics/constraints.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40d6b-111">For more information, see [Generics](./generics/index.md) and [Constraints](./generics/constraints.md).</span></span> <span data-ttu-id="40d6b-112">는 `parameter-list` 생성자 매개 변수를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-112">The `parameter-list` describes constructor parameters.</span></span> <span data-ttu-id="40d6b-113">첫 번째 액세스 한정자는 형식과 관련이 있습니다. 두 번째는 기본 생성자와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-113">The first access modifier pertains to the type; the second pertains to the primary constructor.</span></span> <span data-ttu-id="40d6b-114">두 경우 모두 기본값은 `public` 입니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-114">In both cases, the default is `public`.</span></span>

<span data-ttu-id="40d6b-115">키워드를 사용 하 여 클래스에 대 한 기본 클래스를 지정 합니다 `inherit` .</span><span class="sxs-lookup"><span data-stu-id="40d6b-115">You specify the base class for a class by using the `inherit` keyword.</span></span> <span data-ttu-id="40d6b-116">기본 클래스 생성자에 대 한 인수 (괄호)를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-116">You must supply arguments, in parentheses, for the base class constructor.</span></span>

<span data-ttu-id="40d6b-117">바인딩을 사용 하 여 클래스에 로컬인 필드 또는 함수 값을 선언 하 `let` 고 바인딩에 대 한 일반 규칙을 따라야 합니다 `let` .</span><span class="sxs-lookup"><span data-stu-id="40d6b-117">You declare fields or function values that are local to the class by using `let` bindings, and you must follow the general rules for `let` bindings.</span></span> <span data-ttu-id="40d6b-118">이 `do-bindings` 섹션에는 개체 생성 시 실행 되는 코드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-118">The `do-bindings` section includes code to be executed upon object construction.</span></span>

<span data-ttu-id="40d6b-119">는 `member-list` 추가 생성자, 인스턴스 및 정적 메서드 선언, 인터페이스 선언, 추상 바인딩 및 속성과 이벤트 선언으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-119">The `member-list` consists of additional constructors, instance and static method declarations, interface declarations, abstract bindings, and property and event declarations.</span></span> <span data-ttu-id="40d6b-120">이러한 내용은 [멤버](./members/index.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-120">These are described in [Members](./members/index.md).</span></span>

<span data-ttu-id="40d6b-121">`identifier`선택적 키워드와 함께 사용 되는은 `as` 인스턴스 변수에 대 한 이름을 제공 하 고 형식 정의에서 형식의 인스턴스를 참조 하는 데 사용할 수 있는 자체 식별자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-121">The `identifier` that is used with the optional `as` keyword gives a name to the instance variable, or self identifier, which can be used in the type definition to refer to the instance of the type.</span></span> <span data-ttu-id="40d6b-122">자세한 내용은이 항목의 뒷부분에 나오는 셀프 식별자 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="40d6b-122">For more information, see the section Self Identifiers later in this topic.</span></span>

<span data-ttu-id="40d6b-123">`class` `end` 정의의 시작과 끝을 표시 하는 및 키워드는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-123">The keywords `class` and `end` that mark the start and end of the definition are optional.</span></span>

<span data-ttu-id="40d6b-124">상호 재귀 형식 (서로를 참조 하는 형식)은 `and` 상호 재귀 함수와 마찬가지로 키워드와 함께 조인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-124">Mutually recursive types, which are types that reference each other, are joined together with the `and` keyword just as mutually recursive functions are.</span></span> <span data-ttu-id="40d6b-125">예제는 상호 재귀 형식 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40d6b-125">For an example, see the section Mutually Recursive Types.</span></span>

## <a name="constructors"></a><span data-ttu-id="40d6b-126">생성자</span><span class="sxs-lookup"><span data-stu-id="40d6b-126">Constructors</span></span>

<span data-ttu-id="40d6b-127">생성자는 클래스 형식의 인스턴스를 만드는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-127">The constructor is code that creates an instance of the class type.</span></span> <span data-ttu-id="40d6b-128">클래스에 대 한 생성자는 다른 .NET 언어에서와 같이 F #에서 약간 다르게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-128">Constructors for classes work somewhat differently in F# than they do in other .NET languages.</span></span> <span data-ttu-id="40d6b-129">F # 클래스에는 형식 이름 뒤에 오는에서 인수를 설명 하 `parameter-list` 고, 본문이 `let` `let rec` 클래스 선언의 시작 부분에 있는 (및) 바인딩과 다음에 오는 바인딩으로 구성 된 기본 생성자가 있습니다 `do` .</span><span class="sxs-lookup"><span data-stu-id="40d6b-129">In an F# class, there is always a primary constructor whose arguments are described in the `parameter-list` that follows the type name, and whose body consists of the `let` (and `let rec`) bindings at the start of the class declaration and the `do` bindings that follow.</span></span> <span data-ttu-id="40d6b-130">기본 생성자의 인수는 클래스 선언 전체에서 범위 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-130">The arguments of the primary constructor are in scope throughout the class declaration.</span></span>

<span data-ttu-id="40d6b-131">다음과 같이 키워드를 사용 하 여 추가 생성자를 추가 하 여 멤버를 추가할 수 있습니다 `new` .</span><span class="sxs-lookup"><span data-stu-id="40d6b-131">You can add additional constructors by using the `new` keyword to add a member, as follows:</span></span>

<span data-ttu-id="40d6b-132">`new`(`argument-list`) = `constructor-body`</span><span class="sxs-lookup"><span data-stu-id="40d6b-132">`new`(`argument-list`) = `constructor-body`</span></span>

<span data-ttu-id="40d6b-133">새 생성자의 본문은 클래스 선언 맨 위에 지정 된 기본 생성자를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-133">The body of the new constructor must invoke the primary constructor that is specified at the top of the class declaration.</span></span>

<span data-ttu-id="40d6b-134">다음 예제에서는 이러한 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-134">The following example illustrates this concept.</span></span> <span data-ttu-id="40d6b-135">다음 코드에는 두 개의 `MyClass` 인수를 사용 하는 기본 생성자 인 두 개의 생성자와 인수를 사용 하지 않는 다른 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-135">In the following code, `MyClass` has two constructors, a primary constructor that takes two arguments and another constructor that takes no arguments.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]

## <a name="let-and-do-bindings"></a><span data-ttu-id="40d6b-136">let 및 do 바인딩</span><span class="sxs-lookup"><span data-stu-id="40d6b-136">let and do Bindings</span></span>

<span data-ttu-id="40d6b-137">`let` `do` 클래스 정의의 및 바인딩은 기본 클래스 생성자의 본문을 구성 하므로 클래스 인스턴스가 만들어질 때마다 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-137">The `let` and `do` bindings in a class definition form the body of the primary class constructor, and therefore they run whenever a class instance is created.</span></span> <span data-ttu-id="40d6b-138">바인딩이 함수인 경우에는 `let` 멤버로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-138">If a `let` binding is a function, then it is compiled into a member.</span></span> <span data-ttu-id="40d6b-139">`let`바인딩이 함수 또는 멤버에서 사용 되지 않는 값 이면 생성자에 로컬인 변수로 컴파일됩니다 .이 값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-139">If the `let` binding is a value that is not used in any function or member, then it is compiled into a variable that is local to the constructor.</span></span> <span data-ttu-id="40d6b-140">그렇지 않으면 클래스의 필드로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-140">Otherwise, it is compiled into a field of the class.</span></span> <span data-ttu-id="40d6b-141">`do`다음에 나오는 식은 기본 생성자로 컴파일되고 모든 인스턴스에 대 한 초기화 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-141">The `do` expressions that follow are compiled into the primary constructor and execute initialization code for every instance.</span></span> <span data-ttu-id="40d6b-142">모든 추가 생성자는 항상 기본 생성자를 호출 하므로 `let` `do` 호출 되는 생성자에 관계 없이 바인딩 및 바인딩이 항상 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-142">Because any additional constructors always call the primary constructor, the `let` bindings and `do` bindings always execute regardless of which constructor is called.</span></span>

<span data-ttu-id="40d6b-143">바인딩에서 만든 필드는 `let` 클래스의 메서드 및 속성 전체에서 액세스할 수 있지만 정적 메서드에서 인스턴스 변수를 매개 변수로 사용 하는 경우에도 정적 메서드에서 액세스할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-143">Fields that are created by `let` bindings can be accessed throughout the methods and properties of the class; however, they cannot be accessed from static methods, even if the static methods take an instance variable as a parameter.</span></span> <span data-ttu-id="40d6b-144">자체 식별자 (있는 경우)를 사용 하 여 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-144">They cannot be accessed by using the self identifier, if one exists.</span></span>

## <a name="self-identifiers"></a><span data-ttu-id="40d6b-145">자체 식별자</span><span class="sxs-lookup"><span data-stu-id="40d6b-145">Self Identifiers</span></span>

<span data-ttu-id="40d6b-146">*자체 식별자* 는 현재 인스턴스를 나타내는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-146">A *self identifier* is a name that represents the current instance.</span></span> <span data-ttu-id="40d6b-147">자체 식별자는 `this` c # 또는 c + +의 키워드 또는 Visual Basic와 유사 `Me` 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-147">Self identifiers resemble the `this` keyword in C# or C++ or `Me` in Visual Basic.</span></span> <span data-ttu-id="40d6b-148">자체 식별자를 전체 클래스 정의에 대 한 범위로 할지 아니면 개별 메서드에 대해서만 표시할지에 따라 두 가지 방법으로 자체 식별자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-148">You can define a self identifier in two different ways, depending on whether you want the self identifier to be in scope for the whole class definition or just for an individual method.</span></span>

<span data-ttu-id="40d6b-149">전체 클래스에 대 한 자체 식별자를 정의 하려면 `as` 생성자 매개 변수 목록에서 닫는 괄호 뒤에 키워드를 사용 하 고 식별자 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-149">To define a self identifier for the whole class, use the `as` keyword after the closing parentheses of the constructor parameter list, and specify the identifier name.</span></span>

<span data-ttu-id="40d6b-150">하나의 메서드에 대 한 자체 식별자를 정의 하려면 메서드 이름 바로 앞에 멤버 선언에 자체 식별자를 제공 하 고 구분 기호로 마침표 (.)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-150">To define a self identifier for just one method, provide the self identifier in the member declaration, just before the method name and a period (.) as a separator.</span></span>

<span data-ttu-id="40d6b-151">다음 코드 예제에서는 자체 식별자를 만드는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-151">The following code example illustrates the two ways to create a self identifier.</span></span> <span data-ttu-id="40d6b-152">첫 번째 줄에서 키워드는 `as` 자체 식별자를 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-152">In the first line, the `as` keyword is used to define the self identifier.</span></span> <span data-ttu-id="40d6b-153">다섯 번째 줄에서 식별자는 해당 `this` 범위가 메서드로 제한 되는 자체 식별자를 정의 하는 데 사용 됩니다 `PrintMessage` .</span><span class="sxs-lookup"><span data-stu-id="40d6b-153">In the fifth line, the identifier `this` is used to define a self identifier whose scope is restricted to the method `PrintMessage`.</span></span>

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

<span data-ttu-id="40d6b-154">다른 .NET 언어와 달리 자체 식별자의 이름을 지정할 수 있습니다. , 또는와 같은 이름으로 제한 되지 `self` 않습니다 `Me` `this` .</span><span class="sxs-lookup"><span data-stu-id="40d6b-154">Unlike in other .NET languages, you can name the self identifier however you want; you are not restricted to names such as `self`, `Me`, or `this`.</span></span>

<span data-ttu-id="40d6b-155">키워드를 사용 하 여 선언 된 자체 식별자는 `as` 기본 생성자가 될 때까지 초기화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-155">The self identifier that is declared with the `as` keyword is not initialized until after the base constructor.</span></span> <span data-ttu-id="40d6b-156">따라서 기본 생성자 전후에를 사용 하는 경우 `System.InvalidOperationException: The initialization of an object or value resulted in an object or value being accessed recursively before it was fully initialized.` 런타임 중에이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-156">Therefore, when used before or inside the base constructor, `System.InvalidOperationException: The initialization of an object or value resulted in an object or value being accessed recursively before it was fully initialized.` will be raised during runtime.</span></span> <span data-ttu-id="40d6b-157">바인딩 또는 바인딩과 같은 기본 생성자 뒤에 자체 식별자를 자유롭게 사용할 수 있습니다 `let` `do` .</span><span class="sxs-lookup"><span data-stu-id="40d6b-157">You can use the self identifier freely after the base constructor, such as in `let` bindings or `do` bindings.</span></span>

## <a name="generic-type-parameters"></a><span data-ttu-id="40d6b-158">제네릭 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="40d6b-158">Generic Type Parameters</span></span>

<span data-ttu-id="40d6b-159">제네릭 형식 매개 변수는 꺾쇠 괄호 ( `<` and)로 묶어 작은따옴표로 묶어 작은따옴표 형식으로 지정 `>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-159">Generic type parameters are specified in angle brackets (`<` and `>`), in the form of a single quotation mark followed by an identifier.</span></span> <span data-ttu-id="40d6b-160">여러 제네릭 형식 매개 변수는 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-160">Multiple generic type parameters are separated by commas.</span></span> <span data-ttu-id="40d6b-161">제네릭 형식 매개 변수는 전체 선언 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-161">The generic type parameter is in scope throughout the declaration.</span></span> <span data-ttu-id="40d6b-162">다음 코드 예제에서는 제네릭 형식 매개 변수를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-162">The following code example shows how to specify generic type parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

<span data-ttu-id="40d6b-163">형식을 사용 하는 경우 형식 인수를 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-163">Type arguments are inferred when the type is used.</span></span> <span data-ttu-id="40d6b-164">다음 코드에서는 유추 된 형식이 튜플 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-164">In the following code, the inferred type is a sequence of tuples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]

## <a name="specifying-inheritance"></a><span data-ttu-id="40d6b-165">상속 지정</span><span class="sxs-lookup"><span data-stu-id="40d6b-165">Specifying Inheritance</span></span>

<span data-ttu-id="40d6b-166">`inherit`절은 직접 기본 클래스 (있는 경우)를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-166">The `inherit` clause identifies the direct base class, if there is one.</span></span> <span data-ttu-id="40d6b-167">F #에서는 직접 기본 클래스를 하나만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-167">In F#, only one direct base class is allowed.</span></span> <span data-ttu-id="40d6b-168">클래스가 구현 하는 인터페이스는 기본 클래스로 간주 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-168">Interfaces that a class implements are not considered base classes.</span></span> <span data-ttu-id="40d6b-169">인터페이스에 대 한 자세한 내용은 [인터페이스](Interfaces.md) 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="40d6b-169">Interfaces are discussed in the [Interfaces](Interfaces.md) topic.</span></span>

<span data-ttu-id="40d6b-170">언어 키워드를 `base` 식별자로 사용 하 고 그 뒤에 마침표 (.)와 멤버 이름을 사용 하 여 파생 클래스에서 기본 클래스의 메서드 및 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-170">You can access the methods and properties of the base class from the derived class by using the language keyword `base` as an identifier, followed by a period (.) and the name of the member.</span></span>

<span data-ttu-id="40d6b-171">자세한 내용은 [상속](inheritance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40d6b-171">For more information, see [Inheritance](inheritance.md).</span></span>

## <a name="members-section"></a><span data-ttu-id="40d6b-172">Members 섹션</span><span class="sxs-lookup"><span data-stu-id="40d6b-172">Members Section</span></span>

<span data-ttu-id="40d6b-173">이 섹션에서 정적 또는 인스턴스 메서드, 속성, 인터페이스 구현, 추상 멤버, 이벤트 선언 및 추가 생성자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-173">You can define static or instance methods, properties, interface implementations, abstract members, event declarations, and additional constructors in this section.</span></span> <span data-ttu-id="40d6b-174">Let 및 do 바인딩은이 섹션에 나타날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-174">Let and do bindings cannot appear in this section.</span></span> <span data-ttu-id="40d6b-175">멤버는 클래스 외에도 다양 한 F # 형식에 추가할 수 있으므로 별도 항목인 [멤버](./members/index.md)에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-175">Because members can be added to a variety of F# types in addition to classes, they are discussed in a separate topic, [Members](./members/index.md).</span></span>

## <a name="mutually-recursive-types"></a><span data-ttu-id="40d6b-176">상호 재귀 형식</span><span class="sxs-lookup"><span data-stu-id="40d6b-176">Mutually Recursive Types</span></span>

<span data-ttu-id="40d6b-177">순환 방식으로 서로를 참조 하는 형식을 정의 하는 경우 키워드를 사용 하 여 형식 정의를 함께 문자열 합니다 `and` .</span><span class="sxs-lookup"><span data-stu-id="40d6b-177">When you define types that reference each other in a circular way, you string together the type definitions by using the `and` keyword.</span></span> <span data-ttu-id="40d6b-178">`and`키워드는 `type` 첫 번째 정의를 제외한 모든 키워드를 다음과 같이 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-178">The `and` keyword replaces the `type` keyword on all except the first definition, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

<span data-ttu-id="40d6b-179">출력은 현재 디렉터리에 있는 모든 파일의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-179">The output is a list of all the files in the current directory.</span></span>

## <a name="when-to-use-classes-unions-records-and-structures"></a><span data-ttu-id="40d6b-180">클래스, 공용 구조체, 레코드 및 구조체를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="40d6b-180">When to Use Classes, Unions, Records, and Structures</span></span>

<span data-ttu-id="40d6b-181">선택할 수 있는 다양 한 형식을 고려 하 여 특정 상황에 적합 한 형식을 선택 하기 위해 각 유형을 디자인 하는 방법을 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-181">Given the variety of types to choose from, you need to have a good understanding of what each type is designed for to select the appropriate type for a particular situation.</span></span> <span data-ttu-id="40d6b-182">클래스는 개체 지향 프로그래밍 컨텍스트에서 사용 하도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-182">Classes are designed for use in object-oriented programming contexts.</span></span> <span data-ttu-id="40d6b-183">개체 지향 프로그래밍은 .NET Framework 위해 작성 된 응용 프로그램에서 사용 되는 기준 패러다임입니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-183">Object-oriented programming is the dominant paradigm used in applications that are written for the .NET Framework.</span></span> <span data-ttu-id="40d6b-184">F # 코드가 .NET Framework 또는 다른 개체 지향 라이브러리와 긴밀 하 게 작업 해야 하는 경우, 특히 UI 라이브러리와 같은 개체 지향 형식 시스템에서 확장 해야 하는 경우에는 클래스가 적절할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-184">If your F# code has to work closely with the .NET Framework or another object-oriented library, and especially if you have to extend from an object-oriented type system such as a UI library, classes are probably appropriate.</span></span>

<span data-ttu-id="40d6b-185">개체 지향 코드와 긴밀 하 게 상호 운용 하지 않는 경우 또는 자체 포함 된 코드를 작성 하 여 개체 지향 코드와 자주 상호 작용 하지 않도록 보호 하는 경우에는 레코드 및 구분 된 공용 구조체를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-185">If you are not interoperating closely with object-oriented code, or if you are writing code that is self-contained and therefore protected from frequent interaction with object-oriented code, you should consider using records and discriminated unions.</span></span> <span data-ttu-id="40d6b-186">적절 한 패턴 일치 코드와 함께 잘 생각 되 고 구분 된 단일 합집합을 개체 계층 구조 대신 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-186">A single, well thought–out discriminated union, together with appropriate pattern matching code, can often be used as a simpler alternative to an object hierarchy.</span></span> <span data-ttu-id="40d6b-187">구별 된 공용 구조체에 대 한 자세한 내용은 [구별 된 공용 구조체](discriminated-unions.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40d6b-187">For more information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

<span data-ttu-id="40d6b-188">레코드는 클래스 보다 더 간단 하지만 레코드는 형식 요구가 간단 하 게 수행할 수 있는 작업을 초과 하는 경우에는 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-188">Records have the advantage of being simpler than classes, but records are not appropriate when the demands of a type exceed what can be accomplished with their simplicity.</span></span> <span data-ttu-id="40d6b-189">레코드는 기본적으로 사용자 지정 작업을 수행할 수 있는 별도의 생성자 (숨겨진 필드 없이) 및 상속 또는 인터페이스 구현을 사용 하지 않는 간단한 값의 집계입니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-189">Records are basically simple aggregates of values, without separate constructors that can perform custom actions, without hidden fields, and without inheritance or interface implementations.</span></span> <span data-ttu-id="40d6b-190">속성 및 메서드와 같은 멤버를 레코드에 추가 하 여 동작을 보다 복잡 하 게 만들 수 있지만 레코드에 저장 된 필드는 여전히 값의 단순 집계입니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-190">Although members such as properties and methods can be added to records to make their behavior more complex, the fields stored in a record are still a simple aggregate of values.</span></span> <span data-ttu-id="40d6b-191">레코드에 대 한 자세한 내용은 [레코드](records.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="40d6b-191">For more information about records, see [Records](records.md).</span></span>

<span data-ttu-id="40d6b-192">구조체는 데이터의 작은 집계에도 유용 하지만, .NET 값 형식 이므로 클래스와 레코드와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-192">Structures are also useful for small aggregates of data, but they differ from classes and records in that they are .NET value types.</span></span> <span data-ttu-id="40d6b-193">클래스와 레코드는 .NET 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-193">Classes and records are .NET reference types.</span></span> <span data-ttu-id="40d6b-194">값 형식 및 참조 형식의 의미 체계는 값으로 전달 되는 값 형식에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-194">The semantics of value types and reference types are different in that value types are passed by value.</span></span> <span data-ttu-id="40d6b-195">즉, 매개 변수로 전달 되거나 함수에서 반환 될 때 비트가 비트에 대해 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-195">This means that they are copied bit for bit when they are passed as a parameter or returned from a function.</span></span> <span data-ttu-id="40d6b-196">또한 스택에 저장 되며,이를 필드로 사용 하는 경우 힙의 개별 위치에 저장 되는 대신 부모 개체 내에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-196">They are also stored on the stack or, if they are used as a field, embedded inside the parent object instead of stored in their own separate location on the heap.</span></span> <span data-ttu-id="40d6b-197">따라서 구조는 힙에 액세스 하는 오버 헤드가 문제인 경우 자주 액세스 하는 데이터에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d6b-197">Therefore, structures are appropriate for frequently accessed data when the overhead of accessing the heap is a problem.</span></span> <span data-ttu-id="40d6b-198">구조체에 대 한 자세한 내용은 [구조체](structures.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40d6b-198">For more information about structures, see [Structures](structures.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="40d6b-199">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40d6b-199">See also</span></span>

- [<span data-ttu-id="40d6b-200">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="40d6b-200">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="40d6b-201">멤버</span><span class="sxs-lookup"><span data-stu-id="40d6b-201">Members</span></span>](./members/index.md)
- [<span data-ttu-id="40d6b-202">상속</span><span class="sxs-lookup"><span data-stu-id="40d6b-202">Inheritance</span></span>](inheritance.md)
- [<span data-ttu-id="40d6b-203">인터페이스</span><span class="sxs-lookup"><span data-stu-id="40d6b-203">Interfaces</span></span>](interfaces.md)
