---
description: where(제네릭 형식 제약 조건) - C# 참조
title: where(제네릭 형식 제약 조건) - C# 참조
ms.date: 04/15/2020
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
- classconstraint_CSharpKeyword
- structconstraint_CSharpKeyword
- enumconstraint_CSharpKeyword
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.openlocfilehash: ff2d50b2148ea62e5bef5eceda547a976e4abf02
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687314"
---
# <a name="where-generic-type-constraint-c-reference"></a><span data-ttu-id="9d481-103">where(제네릭 형식 제약 조건)(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="9d481-103">where (generic type constraint) (C# Reference)</span></span>

<span data-ttu-id="9d481-104">제네릭 정의의 `where` 절은 제네릭 형식, 메서드, 대리자 또는 로컬 함수의 형식 매개 변수에 대한 인수로 사용되는 형식에 대한 제약 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-104">The `where` clause in a generic definition specifies constraints on the types that are used as arguments for type parameters in a generic type, method, delegate, or local function.</span></span> <span data-ttu-id="9d481-105">제약 조건은 인터페이스, 기본 클래스를 지정하거나 제네릭 형식을 참조, 값 또는 관리되지 않는 형식으로 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-105">Constraints can specify interfaces, base classes, or require a generic type to be a reference, value, or unmanaged type.</span></span> <span data-ttu-id="9d481-106">형식 인수에 포함해야 하는 기능을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-106">They declare capabilities that the type argument must have.</span></span>

<span data-ttu-id="9d481-107">예를 들어 형식 매개 변수 `T`가 <xref:System.IComparable%601> 인터페이스를 구현하도록 제네릭 클래스 `MyGenericClass`를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-107">For example, you can declare a generic class, `MyGenericClass`, such that the type parameter `T` implements the <xref:System.IComparable%601> interface:</span></span>

[!code-csharp[using an interface constraint](snippets/GenericWhereConstraints.cs#1)]

> [!NOTE]
> <span data-ttu-id="9d481-108">쿼리 식의 where 절에 대한 자세한 내용은 [where 절](where-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d481-108">For more information on the where clause in a query expression, see [where clause](where-clause.md).</span></span>

<span data-ttu-id="9d481-109">`where` 절에는 기본 클래스 제약 조건이 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-109">The `where` clause can also include a base class constraint.</span></span> <span data-ttu-id="9d481-110">기본 클래스 제약 조건에서는 해당 제네릭 형식에 대한 형식 인수로 사용할 형식이 지정된 클래스를 기본 클래스로 포함하거나 해당 기본 클래스임을 명시합니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-110">The base class constraint states that a type to be used as a type argument for that generic type has the specified class as a base class, or is that base class.</span></span> <span data-ttu-id="9d481-111">기본 클래스 제약 조건이 사용되는 경우 해당 형식 매개 변수에 대한 다른 제약 조건 앞에 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-111">If the base class constraint is used, it must appear before any other constraints on that type parameter.</span></span> <span data-ttu-id="9d481-112">일부 형식은 <xref:System.Object>, <xref:System.Array> 및 <xref:System.ValueType> 기본 클래스 제약 조건으로 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-112">Some types are disallowed as a base class constraint: <xref:System.Object>, <xref:System.Array>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="9d481-113">C# 7.3 이전에는 기본 클래스 제약 조건으로 <xref:System.Enum>, <xref:System.Delegate> 및 <xref:System.MulticastDelegate>도 허용되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-113">Before C# 7.3, <xref:System.Enum>, <xref:System.Delegate>, and <xref:System.MulticastDelegate> were also disallowed as base class constraints.</span></span> <span data-ttu-id="9d481-114">다음 예제에서는 이제 기본 클래스로 지정할 수 있는 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-114">The following example shows the types that can now be specified as a base class:</span></span>

[!code-csharp[using an interface constraint](snippets/GenericWhereConstraints.cs#2)]

<span data-ttu-id="9d481-115">C# 8.0 이상의 null 허용 컨텍스트에서는 기본 클래스 형식의 null 허용 여부가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-115">In a nullable context in C# 8.0 and later, the nullability of the base class type is enforced.</span></span> <span data-ttu-id="9d481-116">기본 클래스가 null을 허용하지 않는 경우(예: `Base`) 형식 인수는 null을 허용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-116">If the base class is non-nullable (for example `Base`), the type argument must be non-nullable.</span></span> <span data-ttu-id="9d481-117">기본 클래스가 null을 허용하는 경우(예: `Base?`) 형식 인수는 null을 허용하거나 null을 허용하지 않는 참조 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-117">If the base class is nullable (for example `Base?`), the type argument may be either a nullable or non-nullable reference type.</span></span> <span data-ttu-id="9d481-118">기본 클래스가 null을 허용하지 않는 경우 형식 인수가 null 허용 참조 형식이면 컴파일러가 경고를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-118">The compiler issues a warning if the type argument is a nullable reference type when the base class is non-nullable.</span></span>

<span data-ttu-id="9d481-119">`where` 절은 형식이 `class` 또는 `struct`임을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-119">The `where` clause can specify that the type is a `class` or a `struct`.</span></span> <span data-ttu-id="9d481-120">`struct` 제약 조건은 `System.ValueType`의 기본 클래스 제약 조건을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-120">The `struct` constraint removes the need to specify a base class constraint of `System.ValueType`.</span></span> <span data-ttu-id="9d481-121">`System.ValueType` 형식은 기본 클래스 제약 조건으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-121">The `System.ValueType` type may not be used as a base class constraint.</span></span> <span data-ttu-id="9d481-122">다음 예제에서는 `class` 및 `struct` 제약 조건을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-122">The following example shows both the `class` and `struct` constraints:</span></span>

[!code-csharp[using the class and struct constraints](snippets/GenericWhereConstraints.cs#3)]

<span data-ttu-id="9d481-123">C# 8.0 이상의 null 허용 컨텍스트에서 `class` 제약 조건을 사용하려면 형식이 null을 허용하지 않는 참조 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-123">In a nullable context in C# 8.0 and later, the `class` constraint requires a type to be a non-nullable reference type.</span></span> <span data-ttu-id="9d481-124">null 허용 참조 형식을 허용하려면 null 허용 참조 형식 및 null을 허용하지 않는 참조 형식을 둘 다 허용하는 `class?` 제약 조건을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-124">To allow nullable reference types, use the `class?` constraint, which allows both nullable and non-nullable reference types.</span></span>

<span data-ttu-id="9d481-125">`where` 절은 `notnull` 제약 조건을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-125">The `where` clause may include the `notnull` constraint.</span></span> <span data-ttu-id="9d481-126">`notnull` 제약 조건은 형식 매개 변수를 Null을 허용하지 않는 형식으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-126">The `notnull` constraint limits the type parameter to non-nullable types.</span></span> <span data-ttu-id="9d481-127">해당 형식은 [값 형식](../builtin-types/value-types.md)이거나 nullable이 아닌 참조 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-127">That type may be a [value type](../builtin-types/value-types.md) or a non-nullable reference type.</span></span> <span data-ttu-id="9d481-128">[`nullable enable` 컨텍스트](../../nullable-references.md#nullable-contexts)에서 컴파일된 코드에 대해 C# 8.0부터 `notnull` 제약 조건을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-128">The `notnull` constraint is available starting in C# 8.0 for code compiled in a [`nullable enable` context](../../nullable-references.md#nullable-contexts).</span></span> <span data-ttu-id="9d481-129">다른 제약 조건과 달리 형식 인수가 `notnull` 제약 조건을 위반하면 컴파일러는 오류 대신 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-129">Unlike other constraints, if a type argument violates the `notnull` constraint, the compiler generates a warning instead of an error.</span></span> <span data-ttu-id="9d481-130">경고는 `nullable enable` 컨텍스트에서만 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-130">Warnings are only generated in a `nullable enable` context.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d481-131">`notnull` 제약 조건을 포함하는 제네릭 선언은 nullable 형식을 감지하지 않는 컨텍스트에서 사용될 수 있지만 컴파일러는 제약 조건을 적용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-131">Generic declarations that include the `notnull` constraint can be used in a nullable oblivious context, but compiler does not enforce the constraint.</span></span>

[!code-csharp[using the nonnull constraint](snippets/GenericWhereConstraints.cs#NotNull)]

<span data-ttu-id="9d481-132">`where` 절에 `unmanaged` 제약 조건이 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-132">The `where` clause may also include an `unmanaged` constraint.</span></span> <span data-ttu-id="9d481-133">`unmanaged` 제약 조건은 형식 매개 변수를 [관리되지 않는 형식](../builtin-types/unmanaged-types.md)으로 알려진 형식으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-133">The `unmanaged` constraint limits the type parameter to types known as [unmanaged types](../builtin-types/unmanaged-types.md).</span></span> <span data-ttu-id="9d481-134">`unmanaged` 제약 조건을 사용하면 C#에서 하위 수준의 interop 코드를 더 쉽게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-134">The `unmanaged` constraint makes it easier to write low-level interop code in C#.</span></span> <span data-ttu-id="9d481-135">이 제약 조건을 통해 모든 관리되지 않는 형식에서 재사용 가능한 루틴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-135">This constraint enables reusable routines across all unmanaged types.</span></span> <span data-ttu-id="9d481-136">`unmanaged` 제약 조건은 `class` 또는 `struct` 제약 조건과 결합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-136">The `unmanaged` constraint can't be combined with the `class` or `struct` constraint.</span></span> <span data-ttu-id="9d481-137">`unmanaged` 제약 조건에 따라 형식이 `struct`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-137">The `unmanaged` constraint enforces that the type must be a `struct`:</span></span>

[!code-csharp[using the unmanaged constraint](snippets/GenericWhereConstraints.cs#4)]

<span data-ttu-id="9d481-138">`where` 절에 `new()` 생성자 제약 조건이 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-138">The `where` clause may also include a constructor constraint, `new()`.</span></span> <span data-ttu-id="9d481-139">이 제약 조건을 사용하면 `new` 연산자를 사용하여 형식 매개 변수의 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-139">That constraint makes it possible to create an instance of a type parameter using the `new` operator.</span></span> <span data-ttu-id="9d481-140">[new () 제약 조건](new-constraint.md)을 사용하면 컴파일러에서 제공된 형식 인수에 액세스 가능하고 매개 변수가 없는 생성자가 있어야 한다는 것을 알게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-140">The [new() Constraint](new-constraint.md) lets the compiler know that any type argument supplied must have an accessible parameterless constructor.</span></span> <span data-ttu-id="9d481-141">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="9d481-141">For example:</span></span>

[!code-csharp[using the new constraint](snippets/GenericWhereConstraints.cs#5)]

<span data-ttu-id="9d481-142">`new()` 제약 조건은 `where` 절 맨 끝에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-142">The `new()` constraint appears last in the `where` clause.</span></span> <span data-ttu-id="9d481-143">`new()` 제약 조건은 `struct` 또는 `unmanaged` 제약 조건과 결합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-143">The `new()` constraint can't be combined with the `struct` or `unmanaged` constraints.</span></span> <span data-ttu-id="9d481-144">이러한 제약 조건을 충족하는 모든 형식에는 매개 변수가 없는 액세스 가능 생성자가 있어야 하므로 `new()` 제약 조건이 중복됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-144">All types satisfying those constraints must have an accessible parameterless constructor, making the `new()` constraint redundant.</span></span>

<span data-ttu-id="9d481-145">형식 매개 변수가 여러 개이면 각 형식 매개 변수에 하나의 `where` 절을 사용합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-145">With multiple type parameters, use one `where` clause for each type parameter, for example:</span></span>

[!code-csharp[using multiple where constraints](snippets/GenericWhereConstraints.cs#6)]

<span data-ttu-id="9d481-146">다음 예제와 같이 제약 조건은 제네릭 메서드의 형식 매개 변수에 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-146">You can also attach constraints to type parameters of generic methods, as shown in the following example:</span></span>

[!code-csharp[where constraints with generic methods](snippets/GenericWhereConstraints.cs#7)]

<span data-ttu-id="9d481-147">대리자에 대한 형식 매개 변수 제약 조건을 설명하는 구문은 메서드의 구문과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="9d481-147">Notice that the syntax to describe type parameter constraints on delegates is the same as that of methods:</span></span>

[!code-csharp[where constraints with generic methods](snippets/GenericWhereConstraints.cs#8)]

<span data-ttu-id="9d481-148">제네릭 대리자에 대한 자세한 내용은 [제네릭 대리자](../../programming-guide/generics/generic-delegates.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d481-148">For information on generic delegates, see [Generic Delegates](../../programming-guide/generics/generic-delegates.md).</span></span>

<span data-ttu-id="9d481-149">제약 조건의 구문 및 사용에 대한 자세한 내용은 [형식 매개 변수에 대한 제약 조건](../../programming-guide/generics/constraints-on-type-parameters.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d481-149">For details on the syntax and use of constraints, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9d481-150">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="9d481-150">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="9d481-151">참조</span><span class="sxs-lookup"><span data-stu-id="9d481-151">See also</span></span>

- [<span data-ttu-id="9d481-152">C# 참조</span><span class="sxs-lookup"><span data-stu-id="9d481-152">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9d481-153">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="9d481-153">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9d481-154">제네릭 소개</span><span class="sxs-lookup"><span data-stu-id="9d481-154">Introduction to Generics</span></span>](../../programming-guide/generics/index.md)
- [<span data-ttu-id="9d481-155">new 제약 조건</span><span class="sxs-lookup"><span data-stu-id="9d481-155">new Constraint</span></span>](./new-constraint.md)
- [<span data-ttu-id="9d481-156">형식 매개 변수에 대한 제약 조건</span><span class="sxs-lookup"><span data-stu-id="9d481-156">Constraints on Type Parameters</span></span>](../../programming-guide/generics/constraints-on-type-parameters.md)
