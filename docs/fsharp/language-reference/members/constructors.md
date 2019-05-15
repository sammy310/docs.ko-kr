---
title: 생성자
description: 정의에서 생성자를 사용 하는 방법을 알아봅니다 F# 를 만들고 클래스 및 구조체 개체를 초기화 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: 47fb6e77ce369d7aa4fce3aa2c97ecf7df280c03
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645224"
---
# <a name="constructors"></a><span data-ttu-id="16762-103">생성자</span><span class="sxs-lookup"><span data-stu-id="16762-103">Constructors</span></span>

<span data-ttu-id="16762-104">이 항목 정의 만들고 클래스 및 구조체 개체를 초기화 하려면 생성자를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-104">This topic describes how to define and use constructors to create and initialize class and structure objects.</span></span>

## <a name="construction-of-class-objects"></a><span data-ttu-id="16762-105">클래스 개체 생성</span><span class="sxs-lookup"><span data-stu-id="16762-105">Construction of Class Objects</span></span>

<span data-ttu-id="16762-106">클래스 형식의 개체 생성자가 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="16762-106">Objects of class types have constructors.</span></span> <span data-ttu-id="16762-107">생성자의 두 종류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16762-107">There are two kinds of constructors.</span></span> <span data-ttu-id="16762-108">하나는 매개 변수를 가진 형식 이름 바로 뒤 괄호 안에 표시 하는 기본 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="16762-108">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="16762-109">선택적으로 다른 추가 생성자를 사용 하 여 지정 된 `new` 키워드.</span><span class="sxs-lookup"><span data-stu-id="16762-109">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="16762-110">이러한 추가 생성자는 기본 생성자를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-110">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="16762-111">기본 생성자를 포함 `let` 고 `do` 클래스 정의의 시작 부분에 표시 되는 바인딩.</span><span class="sxs-lookup"><span data-stu-id="16762-111">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="16762-112">A `let` 바인딩 선언 private 필드 및 클래스의 메서드를 `do` 바인딩 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-112">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="16762-113">에 대 한 자세한 내용은 `let` 클래스 생성자에서 바인딩을 참조 [ `let` 클래스에 바인딩](let-bindings-in-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-113">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="16762-114">에 대 한 자세한 내용은 `do` 생성자에 대 한 바인딩 참조 [ `do` 클래스에 바인딩](do-bindings-in-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-114">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="16762-115">여부에 관계 없이 생성자를 호출 하려는 기본 생성자 또는 추가 생성자를 사용 하 여 개체를 만들 수는 `new` 식을 없이 선택적 `new` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="16762-115">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="16762-116">쉼표로 구분 하 여 및 괄호 안에 명명 된 인수 및 값을 사용 하 여 또는 괄호로 묶인 인수를 순서 대로 나열 하는 생성자 인수를 함께 개체를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-116">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="16762-117">또한 및 설정할 수 있습니다 속성 개체에 개체를 생성 하는 동안 속성 이름을 사용 하 여 명명 된 생성자 인수를 사용 하는 것 처럼 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-117">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="16762-118">다음 코드는 생성자 및 개체를 만드는 다양 한 방법을 포함 하는 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16762-118">The following code illustrates a class that has a constructor and various ways of creating objects.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="16762-119">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="16762-119">The output is as follows.</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="16762-120">구조 생성</span><span class="sxs-lookup"><span data-stu-id="16762-120">Construction of Structures</span></span>

<span data-ttu-id="16762-121">구조는 클래스의 모든 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="16762-121">Structures follow all the rules of classes.</span></span> <span data-ttu-id="16762-122">따라서 기본 생성자를 포함할 수 있으며 다른 생성자를 사용 하 여 제공할 수 있습니다 `new`합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-122">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="16762-123">그러나 구조체와 클래스 간의 중요 한 차이점 중 하나는: 없는 기본 생성자가 정의 하는 경우에 구조 (즉, 하나는 인수 없이) 기본 생성자를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16762-123">However, there is one important difference between structures and classes: structures can have a default constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="16762-124">기본 생성자는 해당 형식, 일반적으로 0 또는 해당 기본 값으로 모든 필드를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-124">The default constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="16762-125">구조에 대해 정의한 모든 생성자는 기본 생성자를 사용 하 여 충돌 하지 않도록 인수가 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-125">Any constructors that you define for structures must have at least one argument so that they do not conflict with the default constructor.</span></span>

<span data-ttu-id="16762-126">또한 구조 필드를 사용 하 여 만든를 자주 할는 `val` 키워드; 클래스는 이러한 필드를 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16762-126">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="16762-127">구조체와 클래스를 사용 하 여 정의 된 필드를 있는 `val` 키워드 수 초기화할 수도 추가 생성자의 레코드 식을 사용 하 여 다음 코드와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-127">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="16762-128">자세한 내용은 참조 하세요. [명시적 필드: 합니다 `val` 키워드](explicit-fields-the-val-keyword.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-128">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>

## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="16762-129">생성자의 파생 작업 실행</span><span class="sxs-lookup"><span data-stu-id="16762-129">Executing Side Effects in Constructors</span></span>

<span data-ttu-id="16762-130">클래스에서 기본 생성자의 코드를 실행할 수는 `do` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="16762-130">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="16762-131">그러나 경우에 어떻게 해야 하지 않고 추가 생성자의 코드를 실행 하는 `do` 바인딩?</span><span class="sxs-lookup"><span data-stu-id="16762-131">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="16762-132">이 작업을 수행 하려면 사용 된 `then` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="16762-132">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="16762-133">기본 생성자의 파생 작업이 계속 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-133">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="16762-134">따라서 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="16762-134">Therefore, the output is as follows.</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="16762-135">생성자의 자체 식별자</span><span class="sxs-lookup"><span data-stu-id="16762-135">Self Identifiers in Constructors</span></span>

<span data-ttu-id="16762-136">다른 멤버의 각 멤버의 정의에 있는 현재 개체의 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-136">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="16762-137">사용 하 여 클래스 정의의 첫 번째 줄에서 자체 식별자를 추가할 수도 있습니다는 `as` 키워드 바로 뒤에 생성자 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="16762-137">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="16762-138">다음 예제에서는이 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16762-138">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="16762-139">추가 생성자를 정의할 수도 있습니다 자체 식별자를 넣어는 `as` 생성자 매개 변수 바로 뒤에 절.</span><span class="sxs-lookup"><span data-stu-id="16762-139">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="16762-140">다음 예제에서는이 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16762-140">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="16762-141">완전히 정의 하기 전에 개체를 사용 하려고 할 때 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16762-141">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="16762-142">따라서 자체 식별자의 사용 하 여 경고를 생성 하 고 개체 초기화 되기 전에 개체의 멤버에 액세스 하지 않도록 하는 추가 검사를 삽입 하도록 컴파일러에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16762-142">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="16762-143">자체 식별자만 사용 해야 합니다 `do` 바인딩 후 또는 기본 생성자의는 `then` 추가 생성자의 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="16762-143">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="16762-144">자체 식별자의 이름을 사용할 필요가 없습니다 `this`합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-144">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="16762-145">유효한 식별자 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16762-145">It can be any valid identifier.</span></span>

## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="16762-146">초기화 시 속성에 값 할당</span><span class="sxs-lookup"><span data-stu-id="16762-146">Assigning Values to Properties at Initialization</span></span>

<span data-ttu-id="16762-147">형식의 할당 목록을 추가 하 여 초기화 코드에서 클래스 개체의 속성 값을 할당할 수 있습니다 `property = value` 생성자의 인수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="16762-147">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="16762-148">다음 코드 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16762-148">This is shown in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="16762-149">이전 코드의 다음 버전에서는 일반 인수, 선택적 인수 및 생성자 호출에서 속성 설정의 조합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16762-149">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a><span data-ttu-id="16762-150">상속 된 클래스의 생성자</span><span class="sxs-lookup"><span data-stu-id="16762-150">Constructors in inherited class</span></span>

<span data-ttu-id="16762-151">생성자가 있는 기본 클래스에서 상속 하는 경우에 상속 절에서 인수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-151">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="16762-152">자세한 내용은 [생성자 및 상속](../inheritance.md#constructors-and-inheritance)합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-152">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="16762-153">정적 생성자 또는 형식 생성자</span><span class="sxs-lookup"><span data-stu-id="16762-153">Static Constructors or Type Constructors</span></span>

<span data-ttu-id="16762-154">정적 개체를 만들기 위한 코드를 지정 하는 것 외에도 `let` 고 `do` 바인딩 형식 수준에서 초기화를 수행 하는 형식을 처음으로 사용 하기 전에 실행 되는 클래스 형식에서 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16762-154">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="16762-155">자세한 내용은 참조 하세요. [ `let` 클래스의 바인딩](let-bindings-in-classes.md) 및 [ `do` 클래스에 바인딩](do-bindings-in-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="16762-155">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="16762-156">참고자료</span><span class="sxs-lookup"><span data-stu-id="16762-156">See also</span></span>

- [<span data-ttu-id="16762-157">멤버</span><span class="sxs-lookup"><span data-stu-id="16762-157">Members</span></span>](index.md)
