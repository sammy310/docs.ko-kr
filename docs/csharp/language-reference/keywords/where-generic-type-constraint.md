---
title: where(제네릭 형식 제약 조건) - C# 참조
ms.custom: seodec18
ms.date: 04/12/2018
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.openlocfilehash: 1608cd7b888a67af3ccb98b16323e74a9c5ad4a9
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608403"
---
# <a name="where-generic-type-constraint-c-reference"></a><span data-ttu-id="a6208-102">where(제네릭 형식 제약 조건)(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a6208-102">where (generic type constraint) (C# Reference)</span></span>

<span data-ttu-id="a6208-103">제네릭 정의의 `where` 절은 제네릭 형식, 메서드, 대리자 또는 로컬 함수의 형식 매개 변수에 대한 인수로 사용되는 형식에 대한 제약 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-103">The `where` clause in a generic definition specifies constraints on the types that are used as arguments for type parameters in a generic type, method, delegate, or local function.</span></span> <span data-ttu-id="a6208-104">제약 조건은 인터페이스, 기본 클래스를 지정하거나 제네릭 형식을 참조, 값 또는 관리되지 않는 형식으로 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-104">Constraints can specify interfaces, base classes, or require a generic type to be a reference, value or unmanaged type.</span></span> <span data-ttu-id="a6208-105">형식 인수에서 갖추고 있어야 하는 기능을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-105">They declare capabilities that the type argument must possess.</span></span>

<span data-ttu-id="a6208-106">예를 들어 형식 매개 변수 `T`가 <xref:System.IComparable%601> 인터페이스를 구현하도록 제네릭 클래스 `MyGenericClass`를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-106">For example, you can declare a generic class, `MyGenericClass`, such that the type parameter `T` implements the <xref:System.IComparable%601> interface:</span></span>

[!code-csharp[using an interface constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#1)]

> [!NOTE]
> <span data-ttu-id="a6208-107">쿼리 식의 where 절에 대한 자세한 내용은 [where 절](where-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6208-107">For more information on the where clause in a query expression, see [where clause](where-clause.md).</span></span>

<span data-ttu-id="a6208-108">`where` 절에는 기본 클래스 제약 조건이 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-108">The `where` clause can also include a base class constraint.</span></span> <span data-ttu-id="a6208-109">기본 클래스 제약 조건에서는 해당 제네릭 형식에 대한 형식 인수로 사용할 기본 클래스(또는 해당 기본 클래스)로 지정된 클래스가 해당 제네릭 형식에 대한 형식 인수로 사용할 형식에 있다고 명시합니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-109">The base class constraint states that a type to be used as a type argument for that generic type has the specified class as a base class (or is that base class) to be used as a type argument for that generic type.</span></span> <span data-ttu-id="a6208-110">기본 클래스 제약 조건이 사용되는 경우 해당 형식 매개 변수에 대한 다른 제약 조건 앞에 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-110">If the base class constraint is used, it must appear before any other constraints on that type parameter.</span></span> <span data-ttu-id="a6208-111">일부 형식은 <xref:System.Object>, <xref:System.Array> 및 <xref:System.ValueType> 기본 클래스 제약 조건으로 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-111">Some types are disallowed as a base class constraint: <xref:System.Object>, <xref:System.Array>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="a6208-112">C# 7.3 이전에는 기본 클래스 제약 조건으로 <xref:System.Enum>, <xref:System.Delegate> 및 <xref:System.MulticastDelegate>도 허용되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-112">Prior to C# 7.3, <xref:System.Enum>, <xref:System.Delegate>, and <xref:System.MulticastDelegate> were also disallowed as base class constraints.</span></span> <span data-ttu-id="a6208-113">다음 예제에서는 이제 기본 클래스로 지정할 수 있는 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-113">The following example shows the types that can now be specified as a base class:</span></span>

[!code-csharp[using an interface constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#2)]

<span data-ttu-id="a6208-114">`where` 절은 형식이 `class` 또는 `struct`임을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-114">The `where` clause can specify that the type is a `class` or a `struct`.</span></span> <span data-ttu-id="a6208-115">`struct` 제약 조건은 `System.ValueType`의 기본 클래스 제약 조건을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-115">The `struct` constraint removes the need to specify a base class constraint of `System.ValueType`.</span></span> <span data-ttu-id="a6208-116">`System.ValueType` 형식은 기본 클래스 제약 조건으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-116">The `System.ValueType` type may not be used as a base class constraint.</span></span> <span data-ttu-id="a6208-117">다음 예제에서는 `class` 및 `struct` 제약 조건을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-117">The following example shows both the `class` and `struct` constraints:</span></span>

[!code-csharp[using the class and struct constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#3)]

<span data-ttu-id="a6208-118">`where` 절에 `unmanaged` 제약 조건이 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-118">The `where` clause may also include an `unmanaged` constraint.</span></span> <span data-ttu-id="a6208-119">`unmanaged` 제약 조건은 형식 매개 변수를 [관리되지 않는 형식](../builtin-types/unmanaged-types.md)으로 알려진 형식으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-119">The `unmanaged` constraint limits the type parameter to types known as [unmanaged types](../builtin-types/unmanaged-types.md).</span></span> <span data-ttu-id="a6208-120">`unmanaged` 제약 조건을 사용하면 C#에서 하위 수준의 interop 코드를 더 쉽게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-120">The `unmanaged` constraint makes it easier to write low-level interop code in C#.</span></span> <span data-ttu-id="a6208-121">이 제약 조건을 통해 모든 관리되지 않는 형식에서 재사용 가능한 루틴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-121">This constraint enables reusable routines across all unmanaged types.</span></span> <span data-ttu-id="a6208-122">`unmanaged` 제약 조건은 `class` 또는 `struct` 제약 조건과 결합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-122">The `unmanaged` constraint can't be combined with the `class` or `struct` constraint.</span></span> <span data-ttu-id="a6208-123">`unmanaged` 제약 조건에 따라 형식이 `struct`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-123">The `unmanaged` constraint enforces that the type must be a `struct`:</span></span>

[!code-csharp[using the unmanaged constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#4)]

<span data-ttu-id="a6208-124">`where` 절에 `new()` 생성자 제약 조건이 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-124">The `where` clause may also include a constructor constraint, `new()`.</span></span> <span data-ttu-id="a6208-125">이 제약 조건을 사용하면 `new` 연산자를 사용하여 형식 매개 변수의 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-125">That constraint makes it possible to create an instance of a type parameter using the `new` operator.</span></span> <span data-ttu-id="a6208-126">[new () 제약 조건](new-constraint.md)을 사용하면 컴파일러는 제공된 인수에 액세스 가능하고 매개 변수가 없는 생성자(또는 기본 생성자)가 있어야 한다는 것을 알게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-126">The [new() Constraint](new-constraint.md) lets the compiler know that any type argument supplied must have an accessible parameterless--or default-- constructor.</span></span> <span data-ttu-id="a6208-127">예:</span><span class="sxs-lookup"><span data-stu-id="a6208-127">For example:</span></span>

[!code-csharp[using the new constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#5)]

<span data-ttu-id="a6208-128">`new()` 제약 조건은 `where` 절 맨 끝에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-128">The `new()` constraint appears last in the `where` clause.</span></span> <span data-ttu-id="a6208-129">`new()` 제약 조건은 `struct` 또는 `unmanaged` 제약 조건과 결합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-129">The `new()` constraint can't be combined with the `struct` or `unmanaged` constraints.</span></span> <span data-ttu-id="a6208-130">이러한 제약 조건을 충족하는 모든 형식에는 매개 변수가 없는 액세스 가능 생성자가 있어야 하므로 `new()` 제약 조건이 중복됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-130">All types satisfying those constraints must have an accessible parameterless constructor, making the `new()` constraint redundant.</span></span>

<span data-ttu-id="a6208-131">형식 매개 변수가 여러 개이면 각 형식 매개 변수에 하나의 `where` 절을 사용합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-131">With multiple type parameters, use one `where` clause for each type parameter, for example:</span></span>

[!code-csharp[using multiple where constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#6)]

<span data-ttu-id="a6208-132">다음 예제와 같이 제약 조건은 제네릭 메서드의 형식 매개 변수에 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-132">You can also attach constraints to type parameters of generic methods, as shown in the following example:</span></span>

[!code-csharp[where constraints with generic methods](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#7)]

<span data-ttu-id="a6208-133">대리자에 대한 형식 매개 변수 제약 조건을 설명하는 구문은 메서드의 구문과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="a6208-133">Notice that the syntax to describe type parameter constraints on delegates is the same as that of methods:</span></span>

[!code-csharp[where constraints with generic methods](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#8)]

<span data-ttu-id="a6208-134">제네릭 대리자에 대한 자세한 내용은 [제네릭 대리자](../../programming-guide/generics/generic-delegates.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6208-134">For information on generic delegates, see [Generic Delegates](../../programming-guide/generics/generic-delegates.md).</span></span>

<span data-ttu-id="a6208-135">제약 조건의 구문 및 사용에 대한 자세한 내용은 [형식 매개 변수에 대한 제약 조건](../../programming-guide/generics/constraints-on-type-parameters.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6208-135">For details on the syntax and use of constraints, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a6208-136">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="a6208-136">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a6208-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6208-137">See also</span></span>

- [<span data-ttu-id="a6208-138">C# 참조</span><span class="sxs-lookup"><span data-stu-id="a6208-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a6208-139">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a6208-139">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a6208-140">제네릭 소개</span><span class="sxs-lookup"><span data-stu-id="a6208-140">Introduction to Generics</span></span>](../../programming-guide/generics/index.md)
- [<span data-ttu-id="a6208-141">new 제약 조건</span><span class="sxs-lookup"><span data-stu-id="a6208-141">new Constraint</span></span>](./new-constraint.md)
- [<span data-ttu-id="a6208-142">형식 매개 변수에 대한 제약 조건</span><span class="sxs-lookup"><span data-stu-id="a6208-142">Constraints on Type Parameters</span></span>](../../programming-guide/generics/constraints-on-type-parameters.md)
