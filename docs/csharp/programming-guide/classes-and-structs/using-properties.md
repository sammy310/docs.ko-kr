---
title: 속성 사용 - C# 프로그래밍 가이드
description: 다음 예제에서는 C#의 속성을 사용하는 방법을 보여줍니다. get 및 set 접근자가 읽기 및 쓰기 액세스를 구현하고 속성 사용법을 알아보는 방법을 확인합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- set accessor [C#]
- get accessor [C#]
- properties [C#], about properties
ms.assetid: f7f67b05-0983-4cdb-96af-1855d24c967c
ms.openlocfilehash: 51ca0a37022c99bfbd9d61f2cc47f529d535e72a
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864659"
---
# <a name="using-properties-c-programming-guide"></a><span data-ttu-id="bb8a4-104">속성 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="bb8a4-104">Using Properties (C# Programming Guide)</span></span>

<span data-ttu-id="bb8a4-105">속성은 필드 및 메서드 모두의 측면을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-105">Properties combine aspects of both fields and methods.</span></span> <span data-ttu-id="bb8a4-106">개체의 사용자에게 속성은 필드로 표시되며, 속성에 액세스하려면 동일한 구문이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-106">To the user of an object, a property appears to be a field, accessing the property requires the same syntax.</span></span> <span data-ttu-id="bb8a4-107">클래스의 구현자에게 속성은 [get](../../language-reference/keywords/get.md) 접근자 및/또는 [set](../../language-reference/keywords/set.md) 접근자를 나타내는 하나 또는 두 개의 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-107">To the implementer of a class, a property is one or two code blocks, representing a [get](../../language-reference/keywords/get.md) accessor and/or a [set](../../language-reference/keywords/set.md) accessor.</span></span> <span data-ttu-id="bb8a4-108">`get` 접근자에 대한 코드 블록은 속성을 읽을 때 실행되고, `set` 접근자에 대한 코드 블록은 속성에 새 값을 할당할 때 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-108">The code block for the `get` accessor is executed when the property is read; the code block for the `set` accessor is executed when the property is assigned a new value.</span></span> <span data-ttu-id="bb8a4-109">`set` 접근자가 없는 속성은 읽기 전용으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-109">A property without a `set` accessor is considered read-only.</span></span> <span data-ttu-id="bb8a4-110">`get` 접근자가 없는 속성은 쓰기 전용으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-110">A property without a `get` accessor is considered write-only.</span></span> <span data-ttu-id="bb8a4-111">두 접근자가 모두 있는 속성은 읽기/쓰기입니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-111">A property that has both accessors is read-write.</span></span>

<span data-ttu-id="bb8a4-112">필드와 달리 속성은 변수로 분류되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-112">Unlike fields, properties are not classified as variables.</span></span> <span data-ttu-id="bb8a4-113">따라서 [ref](../../language-reference/keywords/ref.md) 또는 [out](../../language-reference/keywords/out-parameter-modifier.md) 매개 변수로 속성을 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-113">Therefore, you cannot pass a property as a [ref](../../language-reference/keywords/ref.md) or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter.</span></span>

<span data-ttu-id="bb8a4-114">속성은 여러 가지 용도로 사용됩니다. 변경을 허용하기 전에 데이터의 유효성을 검사하고, 데이터가 실제로 데이터베이스 등의 다른 소스에서 검색되는 클래스에 데이터를 투명하게 공개하고, 데이터 변경 시 이벤트 발생, 다른 필드의 값 변경 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-114">Properties have many uses: they can validate data before allowing a change; they can transparently expose data on a class where that data is actually retrieved from some other source, such as a database; they can take an action when data is changed, such as raising an event, or changing the value of other fields.</span></span>

<span data-ttu-id="bb8a4-115">속성은 필드의 액세스 수준, 속성 형식, 속성 이름, `get` 접근자 및/또는 `set` 접근자를 선언하는 코드 블록을 차례로 지정하여 클래스 블록에서 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-115">Properties are declared in the class block by specifying the access level of the field, followed by the type of the property, followed by the name of the property, and followed by a code block that declares a `get`-accessor and/or a `set` accessor.</span></span> <span data-ttu-id="bb8a4-116">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="bb8a4-116">For example:</span></span>

[!code-csharp[csProgGuideProperties#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#7)]

<span data-ttu-id="bb8a4-117">이 예제에서 `Month`는 속성으로 선언되었으므로, `set` 접근자를 통해 `Month` 값이 1에서 12 사이로 설정되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-117">In this example, `Month` is declared as a property so that the `set` accessor can make sure that the `Month` value is set between 1 and 12.</span></span> <span data-ttu-id="bb8a4-118">`Month` 속성은 전용 필드를 사용하여 실제 값을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-118">The `Month` property uses a private field to track the actual value.</span></span> <span data-ttu-id="bb8a4-119">속성 데이터의 실제 위치를 속성의 “백업 저장소”라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-119">The real location of a property's data is often referred to as the property's "backing store."</span></span> <span data-ttu-id="bb8a4-120">일반적으로 속성은 전용 필드를 백업 저장소로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-120">It is common for properties to use private fields as a backing store.</span></span> <span data-ttu-id="bb8a4-121">속성 호출을 통해서만 필드를 변경할 수 있도록 하기 위해 필드는 private로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-121">The field is marked private in order to make sure that it can only be changed by calling the property.</span></span> <span data-ttu-id="bb8a4-122">공용 및 개인 액세스 제한에 대한 자세한 내용은 [액세스 한정자](./access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-122">For more information about public and private access restrictions, see [Access Modifiers](./access-modifiers.md).</span></span>

<span data-ttu-id="bb8a4-123">자동 구현 속성은 간단한 속성 선언을 위해 간소화된 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-123">Auto-implemented properties provide simplified syntax for simple property declarations.</span></span> <span data-ttu-id="bb8a4-124">자세한 내용은 [자동으로 구현된 속성](auto-implemented-properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-124">For more information, see [Auto-Implemented Properties](auto-implemented-properties.md).</span></span>

## <a name="the-get-accessor"></a><span data-ttu-id="bb8a4-125">get 접근자</span><span class="sxs-lookup"><span data-stu-id="bb8a4-125">The get Accessor</span></span>

<span data-ttu-id="bb8a4-126">`get` 접근자 본문은 메서드 본문과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-126">The body of the `get` accessor resembles that of a method.</span></span> <span data-ttu-id="bb8a4-127">속성 형식의 값을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-127">It must return a value of the property type.</span></span> <span data-ttu-id="bb8a4-128">`get` 접근자의 실행은 필드 값을 읽는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-128">The execution of the `get` accessor is equivalent to reading the value of the field.</span></span> <span data-ttu-id="bb8a4-129">예를 들어 `get` 접근자에서 private 변수를 반환하고 최적화가 사용되는 경우 `get` 접근자 메서드 호출이 컴파일러에서 인라인되므로 메서드 호출 오버헤드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-129">For example, when you are returning the private variable from the `get` accessor and optimizations are enabled, the call to the `get` accessor method is inlined by the compiler so there is no method-call overhead.</span></span> <span data-ttu-id="bb8a4-130">그러나 가상 `get` 접근자 메서드는 컴파일러에서 런타임 시 실제로 호출될 수 있는 메서드를 컴파일 시간에 알 수 없기 때문에 인라인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-130">However, a virtual `get` accessor method cannot be inlined because the compiler does not know at compile-time which method may actually be called at run time.</span></span> <span data-ttu-id="bb8a4-131">다음은 전용 필드 `_name`의 값을 반환하는 `get` 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-131">The following is a `get` accessor that returns the value of a private field `_name`:</span></span>

[!code-csharp[csProgGuideProperties#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#8)]

<span data-ttu-id="bb8a4-132">할당 대상을 제외하고 속성을 참조하는 경우 속성 값을 읽기 위해 `get` 접근자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-132">When you reference the property, except as the target of an assignment, the `get` accessor is invoked to read the value of the property.</span></span> <span data-ttu-id="bb8a4-133">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="bb8a4-133">For example:</span></span>

[!code-csharp[csProgGuideProperties#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#9)]

<span data-ttu-id="bb8a4-134">`get` 접근자는 [return](../../language-reference/keywords/return.md) 또는 [throw](../../language-reference/keywords/throw.md) 문으로 끝나야 하며, 제어가 접근자 본문을 벗어날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-134">The `get` accessor must end in a [return](../../language-reference/keywords/return.md) or [throw](../../language-reference/keywords/throw.md) statement, and control cannot flow off the accessor body.</span></span>

<span data-ttu-id="bb8a4-135">`get` 접근자를 사용하여 개체의 상태를 변경하는 것은 잘못된 프로그래밍 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-135">It is a bad programming style to change the state of the object by using the `get` accessor.</span></span> <span data-ttu-id="bb8a4-136">예를 들어 다음 접근자는 `_number` 필드에 액세스할 때마다 개체의 상태가 변경되는 부작용을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-136">For example, the following accessor produces the side effect of changing the state of the object every time that the `_number` field is accessed.</span></span>

[!code-csharp[csProgGuideProperties#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#10)]

<span data-ttu-id="bb8a4-137">`get` 접근자를 사용하여 필드 값을 반환하거나 계산한 후 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-137">The `get` accessor can be used to return the field value or to compute it and return it.</span></span> <span data-ttu-id="bb8a4-138">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="bb8a4-138">For example:</span></span>

[!code-csharp[csProgGuideProperties#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#11)]

<span data-ttu-id="bb8a4-139">앞의 코드 세그먼트에서 `Name` 속성에 값을 할당하지 않으면 `NA` 값이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-139">In the previous code segment, if you do not assign a value to the `Name` property, it will return the value `NA`.</span></span>

## <a name="the-set-accessor"></a><span data-ttu-id="bb8a4-140">set 접근자</span><span class="sxs-lookup"><span data-stu-id="bb8a4-140">The set Accessor</span></span>

<span data-ttu-id="bb8a4-141">`set` 접근자는 반환 형식이 [void](../../language-reference/builtin-types/void.md)인 메서드와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-141">The `set` accessor resembles a method whose return type is [void](../../language-reference/builtin-types/void.md).</span></span> <span data-ttu-id="bb8a4-142">형식이 속성의 형식인 `value`라는 암시적 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-142">It uses an implicit parameter called `value`, whose type is the type of the property.</span></span> <span data-ttu-id="bb8a4-143">다음 예제에서는 `set` 접근자가 `Name` 속성에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-143">In the following example, a `set` accessor is added to the `Name` property:</span></span>

[!code-csharp[csProgGuideProperties#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#12)]

<span data-ttu-id="bb8a4-144">속성에 값을 할당하는 경우 새 값을 제공하는 인수를 사용하여 `set` 접근자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-144">When you assign a value to the property, the `set` accessor is invoked by using an argument that provides the new value.</span></span> <span data-ttu-id="bb8a4-145">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="bb8a4-145">For example:</span></span>

[!code-csharp[csProgGuideProperties#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#13)]

<span data-ttu-id="bb8a4-146">`set` 접근자의 지역 변수 선언에 대해 암시적 매개 변수 이름 `value`를 사용하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-146">It is an error to use the implicit parameter name, `value`, for a local variable declaration in a `set` accessor.</span></span>

## <a name="remarks"></a><span data-ttu-id="bb8a4-147">설명</span><span class="sxs-lookup"><span data-stu-id="bb8a4-147">Remarks</span></span>

<span data-ttu-id="bb8a4-148">속성은 `public`, `private`, `protected`, `internal`, `protected internal` 또는 `private protected`로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-148">Properties can be marked as `public`, `private`, `protected`, `internal`, `protected internal` or `private protected`.</span></span> <span data-ttu-id="bb8a4-149">이러한 액세스 한정자는 클래스 사용자가 속성에 액세스하는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-149">These access modifiers define how users of the class can access the property.</span></span> <span data-ttu-id="bb8a4-150">동일한 속성에 대한 `get` 및 `set` 접근자가 서로 다른 액세스 한정자를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-150">The `get` and `set` accessors for the same property may have different access modifiers.</span></span> <span data-ttu-id="bb8a4-151">예를 들어 `get`은 형식 외부에서 읽기 전용 액세스를 허용하도록 `public`이 되고, `set`은 `private` 또는 `protected`가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-151">For example, the `get` may be `public` to allow read-only access from outside the type, and the `set` may be `private` or `protected`.</span></span> <span data-ttu-id="bb8a4-152">자세한 내용은 [액세스 한정자](./access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-152">For more information, see [Access Modifiers](./access-modifiers.md).</span></span>

<span data-ttu-id="bb8a4-153">`static` 키워드를 사용하여 속성을 정적 속성으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-153">A property may be declared as a static property by using the `static` keyword.</span></span> <span data-ttu-id="bb8a4-154">그러면 클래스의 인스턴스가 없는 경우에도 언제든지 호출자가 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-154">This makes the property available to callers at any time, even if no instance of the class exists.</span></span> <span data-ttu-id="bb8a4-155">자세한 내용은 [static 클래스 및 static 클래스 멤버](./static-classes-and-static-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-155">For more information, see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>

<span data-ttu-id="bb8a4-156">[virtual](../../language-reference/keywords/virtual.md) 키워드를 사용하여 속성을 가상 속성으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-156">A property may be marked as a virtual property by using the [virtual](../../language-reference/keywords/virtual.md) keyword.</span></span> <span data-ttu-id="bb8a4-157">그러면 파생 클래스에서 [override](../../language-reference/keywords/override.md) 키워드를 사용하여 속성 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-157">This enables derived classes to override the property behavior by using the [override](../../language-reference/keywords/override.md) keyword.</span></span> <span data-ttu-id="bb8a4-158">이러한 옵션에 대한 자세한 내용은 [상속](inheritance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-158">For more information about these options, see [Inheritance](inheritance.md).</span></span>

<span data-ttu-id="bb8a4-159">가상 속성을 재정의하는 속성이 [sealed](../../language-reference/keywords/sealed.md)일 수도 있으며, 파생 클래스에 대해 더 이상 가상이 아니도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-159">A property overriding a virtual property can also be [sealed](../../language-reference/keywords/sealed.md), specifying that for derived classes it is no longer virtual.</span></span> <span data-ttu-id="bb8a4-160">마지막으로, 속성을 [abstract](../../language-reference/keywords/abstract.md)로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-160">Lastly, a property can be declared [abstract](../../language-reference/keywords/abstract.md).</span></span> <span data-ttu-id="bb8a4-161">즉, 클래스에 구현이 없으며 파생 클래스가 자체 구현을 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-161">This means that there is no implementation in the class, and derived classes must write their own implementation.</span></span> <span data-ttu-id="bb8a4-162">이러한 옵션에 대한 자세한 내용은 [추상 및 봉인 클래스와 클래스 멤버](abstract-and-sealed-classes-and-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-162">For more information about these options, see [Abstract and Sealed Classes and Class Members](abstract-and-sealed-classes-and-class-members.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bb8a4-163">[static](../../language-reference/keywords/static.md) 속성의 접근자에 [virtual](../../language-reference/keywords/virtual.md), [abstract](../../language-reference/keywords/abstract.md) 또는 [override](../../language-reference/keywords/override.md) 한정자를 사용하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-163">It is an error to use a [virtual](../../language-reference/keywords/virtual.md), [abstract](../../language-reference/keywords/abstract.md), or [override](../../language-reference/keywords/override.md) modifier on an accessor of a [static](../../language-reference/keywords/static.md) property.</span></span>

## <a name="example"></a><span data-ttu-id="bb8a4-164">예제</span><span class="sxs-lookup"><span data-stu-id="bb8a4-164">Example</span></span>

<span data-ttu-id="bb8a4-165">이 예제에서는 인스턴스, 정적 및 읽기 전용 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-165">This example demonstrates instance, static, and read-only properties.</span></span> <span data-ttu-id="bb8a4-166">키보드에서 직원 이름을 받고 `NumberOfEmployees`를 1만큼 증가한 다음 직원 이름과 번호를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-166">It accepts the name of the employee from the keyboard, increments `NumberOfEmployees` by 1, and displays the Employee name and number.</span></span>

[!code-csharp[csProgGuideProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#2)]

## <a name="example"></a><span data-ttu-id="bb8a4-167">예제</span><span class="sxs-lookup"><span data-stu-id="bb8a4-167">Example</span></span>

<span data-ttu-id="bb8a4-168">이 예제에서는 파생 클래스에서 이름이 같은 다른 속성에 의해 숨겨진 기본 클래스의 속성에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-168">This example demonstrates how to access a property in a base class that is hidden by another property that has the same name in a derived class:</span></span>

[!code-csharp[csProgGuideProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#3)]

<span data-ttu-id="bb8a4-169">다음은 앞의 예제에서 중요한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-169">The following are important points in the previous example:</span></span>

- <span data-ttu-id="bb8a4-170">파생 클래스의 `Name` 속성은 기본 클래스의 `Name` 속성을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-170">The property `Name` in the derived class hides the property `Name` in the base class.</span></span> <span data-ttu-id="bb8a4-171">이러한 경우 `new` 한정자는 파생 클래스의 속성 선언에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-171">In such a case, the `new` modifier is used in the declaration of the property in the derived class:</span></span>

     [!code-csharp[csProgGuideProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#4)]  

- <span data-ttu-id="bb8a4-172">`(Employee)` 캐스트는 기본 클래스의 숨겨진 속성에 액세스하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-172">The cast `(Employee)` is used to access the hidden property in the base class:</span></span>

     [!code-csharp[csProgGuideProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#5)]

     <span data-ttu-id="bb8a4-173">멤버를 숨기는 방법에 대한 자세한 내용은 [new 한정자](../../language-reference/keywords/new-modifier.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-173">For more information about hiding members, see the [new Modifier](../../language-reference/keywords/new-modifier.md).</span></span>

## <a name="example"></a><span data-ttu-id="bb8a4-174">예제</span><span class="sxs-lookup"><span data-stu-id="bb8a4-174">Example</span></span>

<span data-ttu-id="bb8a4-175">이 예제에서 두 클래스 `Cube` 및 `Square`는 추상 클래스 `Shape`를 구현하고 해당 abstract `Area` 속성을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-175">In this example, two classes, `Cube` and `Square`, implement an abstract class, `Shape`, and override its abstract `Area` property.</span></span> <span data-ttu-id="bb8a4-176">속성의 [override](../../language-reference/keywords/override.md) 한정자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-176">Note the use of the [override](../../language-reference/keywords/override.md) modifier on the properties.</span></span> <span data-ttu-id="bb8a4-177">프로그램은 변을 입력으로 사용하고 사각형과 정육면체의 면적을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-177">The program accepts the side as an input and calculates the areas for the square and cube.</span></span> <span data-ttu-id="bb8a4-178">또한 면적을 입력으로 사용하고 사각형 및 정육면체의 해당 변을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8a4-178">It also accepts the area as an input and calculates the corresponding side for the square and cube.</span></span>

[!code-csharp[csProgGuideProperties#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#6)]

## <a name="see-also"></a><span data-ttu-id="bb8a4-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb8a4-179">See also</span></span>

- [<span data-ttu-id="bb8a4-180">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="bb8a4-180">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bb8a4-181">속성</span><span class="sxs-lookup"><span data-stu-id="bb8a4-181">Properties</span></span>](properties.md)
- [<span data-ttu-id="bb8a4-182">인터페이스 속성</span><span class="sxs-lookup"><span data-stu-id="bb8a4-182">Interface Properties</span></span>](interface-properties.md)
- [<span data-ttu-id="bb8a4-183">자동으로 구현된 속성</span><span class="sxs-lookup"><span data-stu-id="bb8a4-183">Auto-Implemented Properties</span></span>](auto-implemented-properties.md)
