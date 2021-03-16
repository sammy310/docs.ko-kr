---
title: 레코드 - C# 프로그래밍 가이드
description: 레코드 형식 및 이를 만드는 방법에 관한 자세한 정보
ms.date: 02/26/2021
helpviewer_keywords:
- records [C#]
- C# language, records
ms.openlocfilehash: a45ed08da18e58f11793d6874d7275d9f5216be4
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102260044"
---
# <a name="records-c-programming-guide"></a><span data-ttu-id="4fd1f-103">레코드(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4fd1f-103">Records (C# Programming Guide)</span></span>

<span data-ttu-id="4fd1f-104">[레코드](../../language-reference/builtin-types/record.md)는 데이터 모델을 사용하기 위한 특수 구문 및 동작을 제공하는 [클래스](../../language-reference/keywords/class.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-104">A [record](../../language-reference/builtin-types/record.md) is a [class](../../language-reference/keywords/class.md) that provides special syntax and behavior for working with data models.</span></span> <span data-ttu-id="4fd1f-105">클래스에 관한 자세한 내용은 [클래스(C# 프로그래밍 가이드)](classes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-105">For information about classes, see [Classes (C# Programming Guide)](classes.md).</span></span>

## <a name="when-to-use-records"></a><span data-ttu-id="4fd1f-106">레코드를 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="4fd1f-106">When to use records</span></span>

<span data-ttu-id="4fd1f-107">다음 시나리오에서는 클래스 대신 레코드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-107">Consider using a record in place of a class in the following scenarios:</span></span>

* <span data-ttu-id="4fd1f-108">개체를 변경할 수 없는 참조 형식을 정의하려는 경우</span><span class="sxs-lookup"><span data-stu-id="4fd1f-108">You want to define a reference type for which objects are immutable.</span></span>
* <span data-ttu-id="4fd1f-109">[값 같음](../statements-expressions-operators/equality-comparisons.md#value-equality) 여부에 따라 달라지는 데이터 모델을 정의하려는 경우</span><span class="sxs-lookup"><span data-stu-id="4fd1f-109">You want to define a data model that depends on [value equality](../statements-expressions-operators/equality-comparisons.md#value-equality).</span></span>

### <a name="immutability"></a><span data-ttu-id="4fd1f-110">불변성</span><span class="sxs-lookup"><span data-stu-id="4fd1f-110">Immutability</span></span>

<span data-ttu-id="4fd1f-111">변경할 수 없는 형식은 인스턴스화된 후 개체의 속성 또는 필드 값을 변경하는 것을 방지하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-111">An immutable type is one that prevents you from changing any property or field values of an object after it's instantiated.</span></span> <span data-ttu-id="4fd1f-112">불변성은 형식이 스레드로부터 안전해야 하거나 해시 테이블에서 동일하게 남아 있는 해시 코드를 사용하는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-112">Immutability can be useful when you need a type to be thread-safe or you're depending on a hash code remaining the same in a hash table.</span></span> <span data-ttu-id="4fd1f-113">레코드는 변경할 수 없는 형식을 만들고 사용하기 위한 간결한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-113">Records provide concise syntax for creating and working with immutable types.</span></span>

<span data-ttu-id="4fd1f-114">불변성은 모든 데이터 시나리오에 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-114">Immutability isn't appropriate for all data scenarios.</span></span> <span data-ttu-id="4fd1f-115">예를 들어, [Entity Framework Core](/ef/core/)는 변경할 수 없는 엔터티 형식을 사용한 업데이트를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-115">[Entity Framework Core](/ef/core/), for example, doesn't support updating with immutable entity types.</span></span>

### <a name="value-equality"></a><span data-ttu-id="4fd1f-116">값 같음</span><span class="sxs-lookup"><span data-stu-id="4fd1f-116">Value equality</span></span>

<span data-ttu-id="4fd1f-117">레코드의 경우 값 같음은 형식이 일치하고 모든 속성 및 필드 값이 일치하는 경우 레코드 형식의 두 변수가 같다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-117">For records, value equality means that two variables of a record type are equal if the types match and all property and field values match.</span></span> <span data-ttu-id="4fd1f-118">클래스와 같은 다른 참조 형식의 경우 같음은 [참조 같음](../statements-expressions-operators/equality-comparisons.md#reference-equality)을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-118">For other reference types such as classes, equality means [reference equality](../statements-expressions-operators/equality-comparisons.md#reference-equality).</span></span> <span data-ttu-id="4fd1f-119">즉, 클래스 형식의 두 변수는 같은 개체를 참조하는 경우 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-119">That is, two variables of a class type are equal if they refer to the same object.</span></span> <span data-ttu-id="4fd1f-120">두 레코드 인스턴스의 같음을 확인하는 메서드와 연산자에서 값 같음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-120">Methods and operators that determine equality of two record instances use value equality.</span></span>

<span data-ttu-id="4fd1f-121">일부 데이터 모델은 값 같음을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-121">Not all data models work well with value equality.</span></span> <span data-ttu-id="4fd1f-122">예를 들어, [Entity Framework Core](/ef/core/)는 참조 같음을 사용하여 개념적으로 하나의 엔터티에 해당하는 엔터티 형식의 인스턴스를 하나만 사용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-122">For example, [Entity Framework Core](/ef/core/) depends on reference equality to ensure that it uses only one instance of an entity type for what is conceptually one entity.</span></span> <span data-ttu-id="4fd1f-123">이 이유로 레코드 형식은 Entity Framework Core에서 엔터티 형식으로 사용하기에 적절하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-123">For this reason, record types aren't appropriate for use as entity types in Entity Framework Core.</span></span>

## <a name="how-records-differ-from-classes"></a><span data-ttu-id="4fd1f-124">클래스와 레코드의 차이점</span><span class="sxs-lookup"><span data-stu-id="4fd1f-124">How records differ from classes</span></span>

<span data-ttu-id="4fd1f-125">클래스를 [선언](classes.md#declaring-classes) 및 [인스턴스화](classes.md#creating-objects)하는 동일한 구문을 레코드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-125">The same syntax that [declares](classes.md#declaring-classes) and [instantiates](classes.md#creating-objects) classes can be used with records.</span></span> <span data-ttu-id="4fd1f-126">`class` 키워드를 `record` 키워드로 대체하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-126">Just substitute the `record` keyword for the `class` keyword.</span></span> <span data-ttu-id="4fd1f-127">마찬가지로, 상속 관계를 표현하는 동일한 구문이 레코드에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-127">Likewise, the same syntax for expressing inheritance relationships is supported by records.</span></span> <span data-ttu-id="4fd1f-128">레코드가 클래스와 다른 점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-128">Records differ from classes in the following ways:</span></span>

* <span data-ttu-id="4fd1f-129">[위치 매개 변수](../../language-reference/builtin-types/record.md#positional-syntax-for-property-definition)를 사용하여 변경할 수 없는 속성으로 형식을 만들고 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-129">You can use [positional parameters](../../language-reference/builtin-types/record.md#positional-syntax-for-property-definition) to create and instantiate a type with immutable properties.</span></span>
* <span data-ttu-id="4fd1f-130">클래스에서 참조 같음 또는 같지 않음(예: <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> 및 `==`)을 나타내는 동일한 메서드와 연산자가 레코드에서 [값 같음 또는 같지 않음](../../language-reference/builtin-types/record.md#value-equality)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-130">The same methods and operators that indicate reference equality or inequality in classes (such as <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> and `==`), indicate [value equality or inequality](../../language-reference/builtin-types/record.md#value-equality) in records.</span></span>
* <span data-ttu-id="4fd1f-131">[`with` 식](../../language-reference/builtin-types/record.md#nondestructive-mutation)을 사용하여 선택된 속성에 새 값을 포함하는 변경할 수 없는 개체의 복사본을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-131">You can use a [`with` expression](../../language-reference/builtin-types/record.md#nondestructive-mutation) to create a copy of an immutable object with new values in selected properties.</span></span>
* <span data-ttu-id="4fd1f-132">레코드의 `ToString` 메서드는 개체 형식 이름과 모든 퍼블릭 속성의 이름과 값을 표시하는 형식 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-132">A record's `ToString` method creates a formatted string that shows an object's type name and the names and values of all its public properties.</span></span>
* <span data-ttu-id="4fd1f-133">레코드는 [다른 레코드에서 상속](../../language-reference/builtin-types/record.md#inheritance)될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-133">A record can [inherit from another record](../../language-reference/builtin-types/record.md#inheritance).</span></span> <span data-ttu-id="4fd1f-134">레코드는 클래스에서 상속될 수 없으며 클래스는 레코드에서 상속될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-134">A record can't inherit from a class, and a class can't inherit from a record.</span></span>

## <a name="examples"></a><span data-ttu-id="4fd1f-135">예제</span><span class="sxs-lookup"><span data-stu-id="4fd1f-135">Examples</span></span>

<span data-ttu-id="4fd1f-136">다음 예제에서는 위치 매개 변수를 사용하여 레코드를 선언하고 인스턴스화하는 퍼블릭 레코드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-136">The following example defines a public record that uses positional parameters to declare and instantiate a record.</span></span> <span data-ttu-id="4fd1f-137">그런 다음, 형식 이름 및 속성 값을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-137">It then prints out the type name and property values:</span></span>

:::code language="csharp" source="../../language-reference/builtin-types/snippets/shared/RecordType.cs" id="InstantiatePositional":::

<span data-ttu-id="4fd1f-138">다음 예제에서는 레코드에서 값 같음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-138">The following example demonstrates value equality in records:</span></span>

:::code language="csharp" source="../../language-reference/builtin-types/snippets/shared/RecordType.cs" id="Equality":::

<span data-ttu-id="4fd1f-139">다음 예제에서는 `with` 식을 사용하여 변경할 수 없는 개체를 복사하고 속성 중 하나를 변경하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-139">The following example demonstrates use of a `with` expression to copy an immutable object and change one of the properties:</span></span>

:::code language="csharp" source="../../language-reference/builtin-types/snippets/shared/RecordType.cs" id="WithExpressions":::

<span data-ttu-id="4fd1f-140">자세한 내용은 [레코드(C# 참조)](../../language-reference/builtin-types/record.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-140">For more information, see [Records (C# reference)](../../language-reference/builtin-types/record.md).</span></span>
  
## <a name="c-language-specification"></a><span data-ttu-id="4fd1f-141">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4fd1f-141">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4fd1f-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4fd1f-142">See also</span></span>

- [<span data-ttu-id="4fd1f-143">클래스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4fd1f-143">Classes (C# Programming Guide)</span></span>](classes.md)
- <span data-ttu-id="4fd1f-144">[레코드(C# 참조)](../../language-reference/builtin-types/record.md)</span><span class="sxs-lookup"><span data-stu-id="4fd1f-144">[Records (C# reference)](../../language-reference/builtin-types/record.md).</span></span>
- [<span data-ttu-id="4fd1f-145">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4fd1f-145">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4fd1f-146">개체 지향 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="4fd1f-146">Object-Oriented Programming</span></span>](../../tutorials/intro-to-csharp/object-oriented-programming.md)
- [<span data-ttu-id="4fd1f-147">다형성</span><span class="sxs-lookup"><span data-stu-id="4fd1f-147">Polymorphism</span></span>](polymorphism.md)
- [<span data-ttu-id="4fd1f-148">식별자 이름</span><span class="sxs-lookup"><span data-stu-id="4fd1f-148">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="4fd1f-149">멤버</span><span class="sxs-lookup"><span data-stu-id="4fd1f-149">Members</span></span>](members.md)
- [<span data-ttu-id="4fd1f-150">메서드</span><span class="sxs-lookup"><span data-stu-id="4fd1f-150">Methods</span></span>](methods.md)
- [<span data-ttu-id="4fd1f-151">생성자</span><span class="sxs-lookup"><span data-stu-id="4fd1f-151">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="4fd1f-152">종료자</span><span class="sxs-lookup"><span data-stu-id="4fd1f-152">Finalizers</span></span>](destructors.md)
- [<span data-ttu-id="4fd1f-153">개체</span><span class="sxs-lookup"><span data-stu-id="4fd1f-153">Objects</span></span>](objects.md)
