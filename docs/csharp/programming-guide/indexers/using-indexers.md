---
title: 인덱서 사용 - C# 프로그래밍 가이드
description: C#에서 클래스, 구조체 또는 인터페이스에 대한 인덱서를 선언하고 사용하는 방법을 알아봅니다. 이 문서에는 예제 코드가 포함되어 있습니다.
ms.date: 07/15/2020
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: a8a9e05c1d2e44841177a924c6ff51c6c9e6a05a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301868"
---
# <a name="using-indexers-c-programming-guide"></a><span data-ttu-id="f18a8-104">인덱서 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="f18a8-104">Using indexers (C# Programming Guide)</span></span>

<span data-ttu-id="f18a8-105">인덱서는 클라이언트 애플리케이션이 배열처럼 액세스할 수 있는 [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), [interface](../../language-reference/keywords/interface.md)를 만들 수 있게 해주는 편리한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-105">Indexers are a syntactic convenience that enable you to create a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), or [interface](../../language-reference/keywords/interface.md) that client applications can access as an array.</span></span> <span data-ttu-id="f18a8-106">컴파일러는 `Item` 속성(또는 <xref:System.Runtime.CompilerServices.IndexerNameAttribute>가 있는 경우 달리 명명된 속성) 및 적절한 접근자 메서드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-106">The compiler will generate an `Item` property (or an alternatively named property if <xref:System.Runtime.CompilerServices.IndexerNameAttribute> is present), and the appropriate accessor methods.</span></span> <span data-ttu-id="f18a8-107">인덱서는 내부 컬렉션 또는 배열을 캡슐화하는 데 주로 사용되는 형식에서 자주 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-107">Indexers are most frequently implemented in types whose primary purpose is to encapsulate an internal collection or array.</span></span> <span data-ttu-id="f18a8-108">예를 들어 24시간 동안 10회 기록된 화씨온도를 나타내는 `TempRecord` 클래스가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-108">For example, suppose you have a class `TempRecord` that represents the temperature in Fahrenheit as recorded at 10 different times during a 24-hour period.</span></span> <span data-ttu-id="f18a8-109">이 클래스에는 온도 값을 저장할 `float[]` 형식의 `temps` 배열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-109">The class contains a `temps` array of type `float[]` to store the temperature values.</span></span> <span data-ttu-id="f18a8-110">이 클래스에서 인덱서를 구현하면 클라이언트가 `TempRecord` 인스턴스의 온도에 `float temp = tempRecord.temps[4]` 대신 `float temp = tempRecord[4]`로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-110">By implementing an indexer in this class, clients can access the temperatures in a `TempRecord` instance as `float temp = tempRecord[4]` instead of as `float temp = tempRecord.temps[4]`.</span></span> <span data-ttu-id="f18a8-111">인덱서 표기법은 클라이언트 애플리케이션에 대한 구문을 간소화할 뿐 아니라 클래스와 해당 용도를 다른 개발자가 이해하기 쉽게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-111">The indexer notation not only simplifies the syntax for client applications; it also makes the class, and its purpose more intuitive for other developers to understand.</span></span>

<span data-ttu-id="f18a8-112">클래스 또는 구조체에서 인덱서를 선언하려면 다음 예제에 표시된 대로 [this](../../language-reference/keywords/this.md) 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-112">To declare an indexer on a class or struct, use the [this](../../language-reference/keywords/this.md) keyword, as the following example shows:</span></span>

```csharp
// Indexer declaration
public int this[int index]
{
    // get and set accessors
}
```

> [!IMPORTANT]
> <span data-ttu-id="f18a8-113">인덱서를 선언하면 개체에 `Item`이라는 속성이 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-113">Declaring an indexer will automatically generate a property named `Item` on the object.</span></span> <span data-ttu-id="f18a8-114">`Item` 속성은 [멤버 액세스 식](../../language-reference/operators/member-access-operators.md#member-access-expression-) 인스턴스에서 직접 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-114">The `Item` property is not directly accessible from the instance [member access expression](../../language-reference/operators/member-access-operators.md#member-access-expression-).</span></span> <span data-ttu-id="f18a8-115">또한 인덱서를 사용하여 `Item` 속성을 개체에 추가하는 경우 [CS0102 컴파일러 오류](../../misc/cs0102.md)가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-115">Additionally, if you add your own `Item` property to an object with an indexer, you'll get a [CS0102 compiler error](../../misc/cs0102.md).</span></span> <span data-ttu-id="f18a8-116">이 오류를 방지하려면 아래에 설명된 대로 <xref:System.Runtime.CompilerServices.IndexerNameAttribute>를 사용하여 인덱서 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-116">To avoid this error, use the <xref:System.Runtime.CompilerServices.IndexerNameAttribute> rename the indexer as detailed below.</span></span>

## <a name="remarks"></a><span data-ttu-id="f18a8-117">설명</span><span class="sxs-lookup"><span data-stu-id="f18a8-117">Remarks</span></span>

<span data-ttu-id="f18a8-118">인덱서의 형식과 해당 매개 변수의 형식은 최소한 인덱서 자체만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-118">The type of an indexer and the type of its parameters must be at least as accessible as the indexer itself.</span></span> <span data-ttu-id="f18a8-119">접근성 수준에 대한 자세한 내용은 [액세스 한정자](../../language-reference/keywords/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f18a8-119">For more information about accessibility levels, see [Access Modifiers](../../language-reference/keywords/access-modifiers.md).</span></span>

<span data-ttu-id="f18a8-120">인터페이스와 함께 인덱서를 사용하는 방법에 대한 자세한 내용은 [인터페이스 인덱서](./indexers-in-interfaces.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f18a8-120">For more information about how to use indexers with an interface, see [Interface Indexers](./indexers-in-interfaces.md).</span></span>

<span data-ttu-id="f18a8-121">인덱서의 시그니처는 정식 매개 변수의 형식 및 개수로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-121">The signature of an indexer consists of the number and types of its formal parameters.</span></span> <span data-ttu-id="f18a8-122">정식 매개 변수의 이름이나 인덱서 형식은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-122">It doesn't include the indexer type or the names of the formal parameters.</span></span> <span data-ttu-id="f18a8-123">동일한 클래스에서 둘 이상의 인덱서를 선언하는 경우 다른 시그니처가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-123">If you declare more than one indexer in the same class, they must have different signatures.</span></span>

<span data-ttu-id="f18a8-124">인덱서 값은 변수로 분류되지 않으므로 인덱서 값을 [ref](../../language-reference/keywords/ref.md) 또는 [out](../../language-reference/keywords/out-parameter-modifier.md) 매개 변수로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-124">An indexer value is not classified as a variable; therefore, you cannot pass an indexer value as a [ref](../../language-reference/keywords/ref.md) or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter.</span></span>

<span data-ttu-id="f18a8-125">다른 언어에서 사용할 수 있는 이름을 인덱서에 제공하려면 다음 예제에 표시된 대로 <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-125">To provide the indexer with a name that other languages can use, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, as the following example shows:</span></span>

```csharp
// Indexer declaration
[System.Runtime.CompilerServices.IndexerName("TheItem")]
public int this[int index]
{
    // get and set accessors
}
```

<span data-ttu-id="f18a8-126">이 인덱서는 인덱서 이름 특성으로 재정의되므로 `TheItem`이라는 이름을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-126">This indexer will have the name `TheItem`, as it is overridden by the indexer name attribute.</span></span> <span data-ttu-id="f18a8-127">기본적으로 인덱서 이름은 `Item`입니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-127">By default, the indexer name is `Item`.</span></span>

## <a name="example-1"></a><span data-ttu-id="f18a8-128">예제 1</span><span class="sxs-lookup"><span data-stu-id="f18a8-128">Example 1</span></span>

<span data-ttu-id="f18a8-129">다음 예제에서는 전용 배열 필드, `temps`, 인덱서를 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-129">The following example shows how to declare a private array field, `temps`, and an indexer.</span></span> <span data-ttu-id="f18a8-130">인덱서를 사용하면 `tempRecord[i]` 인스턴스에 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-130">The indexer enables direct access to the instance `tempRecord[i]`.</span></span> <span data-ttu-id="f18a8-131">인덱서를 사용하지 않으려면 배열을 [public](../../language-reference/keywords/public.md) 멤버로 선언하고 해당 멤버인 `tempRecord.temps[i]`에 직접 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-131">The alternative to using the indexer is to declare the array as a [public](../../language-reference/keywords/public.md) member and access its members, `tempRecord.temps[i]`, directly.</span></span>

:::code language="csharp" source="snippets/Temperatures/TempRecord.cs":::

<span data-ttu-id="f18a8-132">인덱서의 액세스가 `Console.Write` 문 등에서 평가될 때 [get](../../language-reference/keywords/get.md) 접근자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-132">Notice that when an indexer's access is evaluated, for example, in a `Console.Write` statement, the [get](../../language-reference/keywords/get.md) accessor is invoked.</span></span> <span data-ttu-id="f18a8-133">따라서 `get` 접근자가 없으면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-133">Therefore, if no `get` accessor exists, a compile-time error occurs.</span></span>

:::code language="csharp" source="snippets/Temperatures/Program.cs":::

## <a name="indexing-using-other-values"></a><span data-ttu-id="f18a8-134">다른 값을 사용하여 인덱싱</span><span class="sxs-lookup"><span data-stu-id="f18a8-134">Indexing using other values</span></span>

<span data-ttu-id="f18a8-135">C#은 인덱스 매개 변수 형식을 정수로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-135">C# doesn't limit the indexer parameter type to integer.</span></span> <span data-ttu-id="f18a8-136">예를 들어 인덱서와 함께 문자열을 사용하면 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-136">For example, it may be useful to use a string with an indexer.</span></span> <span data-ttu-id="f18a8-137">이러한 인덱서는 컬렉션에서 문자열을 검색하고 적절한 값을 반환하여 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-137">Such an indexer might be implemented by searching for the string in the collection, and returning the appropriate value.</span></span> <span data-ttu-id="f18a8-138">접근자를 오버로드할 수 있기 때문에 문자열 및 정수 버전을 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-138">As accessors can be overloaded, the string and integer versions can coexist.</span></span>

## <a name="example-2"></a><span data-ttu-id="f18a8-139">예제 2</span><span class="sxs-lookup"><span data-stu-id="f18a8-139">Example 2</span></span>

<span data-ttu-id="f18a8-140">다음 예제에서는 요일을 저장하는 클래스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-140">The following example declares a class that stores the days of the week.</span></span> <span data-ttu-id="f18a8-141">`get` 접근자는 문자열인 요일 이름을 사용하고 해당 정수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-141">A `get` accessor takes a string, the name of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="f18a8-142">예를 들어 “일요일”이면 0을 반환하고, “월요일”이면 1을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-142">For example, "Sunday" returns 0, "Monday" returns 1, and so on.</span></span>

:::code language="csharp" source="snippets/StringIndexers/DayCollection.cs":::

### <a name="consuming-example-2"></a><span data-ttu-id="f18a8-143">예제 2 사용</span><span class="sxs-lookup"><span data-stu-id="f18a8-143">Consuming example 2</span></span>

:::code language="csharp" source="snippets/StringIndexers/Program.cs":::

## <a name="example-3"></a><span data-ttu-id="f18a8-144">예제 3</span><span class="sxs-lookup"><span data-stu-id="f18a8-144">Example 3</span></span>

<span data-ttu-id="f18a8-145">다음 예제에서는 <xref:System.DayOfWeek?displayProperty=fullName> 열거형을 사용하여 요일을 저장하는 클래스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-145">The following example declares a class that stores the days of the week using the <xref:System.DayOfWeek?displayProperty=fullName> enum.</span></span> <span data-ttu-id="f18a8-146">`get` 접근자는 요일 값인 `DayOfWeek`를 사용하고 해당 정수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-146">A `get` accessor takes a `DayOfWeek`, the value of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="f18a8-147">예를 들어 `DayOfWeek.Sunday`는 0을 반환하고 `DayOfWeek.Monday`는 1을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-147">For example, `DayOfWeek.Sunday` returns 0, `DayOfWeek.Monday` returns 1, and so on.</span></span>

:::code language="csharp" source="snippets/DayOfWeekIndexers/DayOfWeekCollection.cs":::

### <a name="consuming-example-3"></a><span data-ttu-id="f18a8-148">예제 3 사용</span><span class="sxs-lookup"><span data-stu-id="f18a8-148">Consuming example 3</span></span>

:::code language="csharp" source="snippets/DayOfWeekIndexers/Program.cs":::

## <a name="robust-programming"></a><span data-ttu-id="f18a8-149">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="f18a8-149">Robust programming</span></span>

<span data-ttu-id="f18a8-150">인덱서의 보안과 안정성을 향상할 수 있는 다음 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-150">There are two main ways in which the security and reliability of indexers can be improved:</span></span>

- <span data-ttu-id="f18a8-151">클라이언트 코드에서 잘못된 인덱스 값을 전달할 가능성을 처리하는 일부 유형의 오류 처리 전략을 통합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-151">Be sure to incorporate some type of error-handling strategy to handle the chance of client code passing in an invalid index value.</span></span> <span data-ttu-id="f18a8-152">이 항목의 앞부분에 있는 첫 번째 예제에서 TempRecord 클래스는 클라이언트 코드에서 입력을 인덱서에 전달하기 전에 확인할 수 있게 해주는 Length 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-152">In the first example earlier in this topic, the TempRecord class provides a Length property that enables the client code to verify the input before passing it to the indexer.</span></span> <span data-ttu-id="f18a8-153">인덱서 자체 안에 오류 처리 코드를 넣을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-153">You can also put the error handling code inside the indexer itself.</span></span> <span data-ttu-id="f18a8-154">사용자를 위해 인덱서 접근자 내에서 throw하는 모든 예외를 문서화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-154">Be sure to document for users any exceptions that you throw inside an indexer accessor.</span></span>

- <span data-ttu-id="f18a8-155">[get](../../language-reference/keywords/get.md) 및 [set](../../language-reference/keywords/set.md) 접근자의 접근성을 적절하게 제한적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-155">Set the accessibility of the [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessors to be as restrictive as is reasonable.</span></span> <span data-ttu-id="f18a8-156">특히 `set` 접근자의 경우 이 작업이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="f18a8-156">This is important for the `set` accessor in particular.</span></span> <span data-ttu-id="f18a8-157">자세한 내용은 [접근자 액세스 가능성 제한](../classes-and-structs/restricting-accessor-accessibility.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f18a8-157">For more information, see [Restricting Accessor Accessibility](../classes-and-structs/restricting-accessor-accessibility.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f18a8-158">참조</span><span class="sxs-lookup"><span data-stu-id="f18a8-158">See also</span></span>

- [<span data-ttu-id="f18a8-159">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f18a8-159">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f18a8-160">인덱서</span><span class="sxs-lookup"><span data-stu-id="f18a8-160">Indexers</span></span>](./index.md)
- [<span data-ttu-id="f18a8-161">속성</span><span class="sxs-lookup"><span data-stu-id="f18a8-161">Properties</span></span>](../classes-and-structs/properties.md)
