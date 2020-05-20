---
title: C# 6의 새로운 기능 - C# 가이드
description: C# 버전 6의 새로운 기능을 알아봅니다.
ms.date: 12/12/2018
ms.openlocfilehash: da40b4c9d4af0094fdd907c542e971ba55086e0f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398156"
---
# <a name="whats-new-in-c-6"></a><span data-ttu-id="b9ac6-103">C# 6의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="b9ac6-103">What's New in C# 6</span></span>

<span data-ttu-id="b9ac6-104">C#의 6.0 릴리스에는 개발자의 생산성을 개선하는 많은 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-104">The 6.0 release of C# contained many features that improve productivity for developers.</span></span> <span data-ttu-id="b9ac6-105">이러한 기능의 전반적인 영향은 더 읽기 쉬운 더 간결한 코드를 작성한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-105">The overall effect of these features is that you write more concise code that is also more readable.</span></span> <span data-ttu-id="b9ac6-106">많은 일반적인 사례에 대한 더 적은 의례가 구문에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-106">The syntax contains less ceremony for many common practices.</span></span> <span data-ttu-id="b9ac6-107">더 적은 의례로 디자인 의도를 더 쉽게 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-107">It's easier to see the design intent with less ceremony.</span></span> <span data-ttu-id="b9ac6-108">이러한 기능을 자세히 알아보세요. 생산성을 높이고 더 가독성이 높은 코드를 작성할 수 있을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-108">Learn these features well, and you'll be more productive and write more readable code.</span></span> <span data-ttu-id="b9ac6-109">언어의 구문보다 기능에 더 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-109">You can concentrate more on your features than on the constructs of the language.</span></span>

<span data-ttu-id="b9ac6-110">이 문서의 나머지 부분에서는 이러한 각 기능을 간략히 설명하고 이러한 기능을 살펴볼 수 있는 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-110">The rest of this article provides an overview of each of these features, with a link to explore each feature.</span></span> <span data-ttu-id="b9ac6-111">또한 자습서 섹션의 [C# 6에 대한 대화형 살펴보기](../tutorials/exploration/csharp-6.yml)에서 기능을 살펴볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-111">You can also explore the features in an [interactive exploration on C# 6](../tutorials/exploration/csharp-6.yml) in the tutorials section.</span></span>

## <a name="read-only-auto-properties"></a><span data-ttu-id="b9ac6-112">읽기 전용 auto 속성</span><span class="sxs-lookup"><span data-stu-id="b9ac6-112">Read-only auto-properties</span></span>

<span data-ttu-id="b9ac6-113">*읽기 전용 auto 속성*은 변경할 수 없는 형식을 만드는 더 간결한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-113">*Read-only auto-properties* provide a more concise syntax to create immutable types.</span></span> <span data-ttu-id="b9ac6-114">get 접근자만 사용하여 auto 속성을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-114">You declare the auto-property with only a get accessor:</span></span>

[!code-csharp[ReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoProperty)]

<span data-ttu-id="b9ac6-115">`FirstName` 및 `LastName` 속성은 동일한 클래스의 생성자 본문에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-115">The `FirstName` and `LastName` properties can be set only in the body of the constructor of the same class:</span></span>

[!code-csharp[ReadOnlyAutoPropertyConstructor](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoPropertyConstructor)]

<span data-ttu-id="b9ac6-116">다른 메서드에서 `LastName`을 설정하려고 하면 `CS0200` 컴파일 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-116">Trying to set `LastName` in another method generates a `CS0200` compilation error:</span></span>

```csharp
public class Student
{
    public string LastName { get;  }

    public void ChangeName(string newLastName)
    {
        // Generates CS0200: Property or indexer cannot be assigned to -- it is read only
        LastName = newLastName;
    }
}
```

<span data-ttu-id="b9ac6-117">이 기능은 변경할 수 없는 형식을 만들기 위한 실제 언어 지원을 구현하고, 더 간결하고 편리한 auto 속성 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-117">This feature enables true language support for creating immutable types and uses the more concise and convenient auto-property syntax.</span></span>

<span data-ttu-id="b9ac6-118">이 구문을 추가해도 액세스 가능 메서드가 제거되지 않으면 [이진 호환 가능 변경](version-update-considerations.md#binary-compatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-118">If adding this syntax doesn't remove an accessible method, it's a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>

## <a name="auto-property-initializers"></a><span data-ttu-id="b9ac6-119">Auto 속성 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="b9ac6-119">Auto-property initializers</span></span>

<span data-ttu-id="b9ac6-120">‘Auto 속성 이니셜라이저’를 통해 속성 선언의 일부로 auto 속성의 초기 값을 선언할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="b9ac6-120">*Auto-property initializers* let you declare the initial value for an auto-property as part of the property declaration.</span></span>

[!code-csharp[Initialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#Initialization)]

<span data-ttu-id="b9ac6-121">`Grades` 멤버는 선언된 위치에서 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-121">The `Grades` member is initialized where it's declared.</span></span> <span data-ttu-id="b9ac6-122">따라서 더 쉽게 정확히 한 번 초기화를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-122">That makes it easier to perform the initialization exactly once.</span></span> <span data-ttu-id="b9ac6-123">초기화가 속성 선언의 일부이므로 `Student` 개체에 대한 public 인터페이스를 통해 스토리지를 균등하게 할당하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-123">The initialization is part of the property declaration, making it easier to equate the storage allocation with the public interface for `Student` objects.</span></span>

## <a name="expression-bodied-function-members"></a><span data-ttu-id="b9ac6-124">식 본문 함수 멤버</span><span class="sxs-lookup"><span data-stu-id="b9ac6-124">Expression-bodied function members</span></span>

<span data-ttu-id="b9ac6-125">개발자가 작성하는 많은 멤버는 단일 식이 될 수 있는 단일 명령문입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-125">Many members that you write are single statements that could be single expressions.</span></span> <span data-ttu-id="b9ac6-126">대신 식 본문 멤버를 작성하세요.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-126">Write an expression-bodied member instead.</span></span> <span data-ttu-id="b9ac6-127">이 내용은 메서드 및 읽기 전용 속성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-127">It works for methods and read-only properties.</span></span> <span data-ttu-id="b9ac6-128">예를 들어 `ToString()`의 재정의가 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-128">For example, an override of `ToString()` is often a great candidate:</span></span>

[!code-csharp[ToStringExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#ToStringExpressionMember)]

<span data-ttu-id="b9ac6-129">또한 읽기 전용 속성에 이 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-129">You can also use this syntax for read-only properties:</span></span>

[!code-csharp[FullNameExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

<span data-ttu-id="b9ac6-130">기존 멤버를 식 본문 멤버로 변경하는 것은 [이진 호환 가능 변경](version-update-considerations.md#binary-compatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-130">Changing an existing member to an expression bodied member is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>

## <a name="using-static"></a><span data-ttu-id="b9ac6-131">using static</span><span class="sxs-lookup"><span data-stu-id="b9ac6-131">using static</span></span>

<span data-ttu-id="b9ac6-132">*using static* 향상된 기능을 사용하여 단일 클래스의 정적 메서드를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-132">The *using static* enhancement enables you to import the static methods of a single class.</span></span> <span data-ttu-id="b9ac6-133">사용 중인 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-133">You specify the class you're using:</span></span>

[!code-csharp[UsingStaticMath](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticMath)]

<span data-ttu-id="b9ac6-134"><xref:System.Math>에는 인스턴스 메서드가 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-134">The <xref:System.Math> does not contain any instance methods.</span></span> <span data-ttu-id="b9ac6-135">`using static`을 사용하여 정적 및 인스턴스 메서드가 둘 다 포함된 클래스에 대한 클래스의 정적 메서드를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-135">You can also use `using static` to import a class' static methods for a class that has both static and instance methods.</span></span> <span data-ttu-id="b9ac6-136">가장 유용한 예 중 하나는 <xref:System.String>입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-136">One of the most useful examples is <xref:System.String>:</span></span>

[!code-csharp[UsingStatic](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStatic)]

> [!NOTE]
> <span data-ttu-id="b9ac6-137">static using 문에서는 정규화된 클래스 이름 `System.String`을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-137">You must use the fully qualified class name, `System.String`  in a static using statement.</span></span>  <span data-ttu-id="b9ac6-138">대신 `string` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-138">You cannot use the `string` keyword instead.</span></span>

<span data-ttu-id="b9ac6-139">`static using` 문에서 가져온 확장 메서드는 확장 메서드 호출 구문을 사용하여 호출될 때만 범위 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-139">When imported from a `static using` statement, extension methods are only in scope when called using the extension method invocation syntax.</span></span> <span data-ttu-id="b9ac6-140">정적 메서드로 호출될 때는 범위 내에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-140">They aren't in scope when called as a static method.</span></span> <span data-ttu-id="b9ac6-141">일반적으로 LINQ 쿼리에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-141">You'll often see this in LINQ queries.</span></span> <span data-ttu-id="b9ac6-142"><xref:System.Linq.Enumerable> 또는 <xref:System.Linq.Queryable>을 가져와 LINQ 패턴을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-142">You can import the LINQ pattern by importing <xref:System.Linq.Enumerable>, or <xref:System.Linq.Queryable>.</span></span>

[!code-csharp[UsingStaticLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#usingStaticLinq)]

<span data-ttu-id="b9ac6-143">일반적으로 확장 메서드는 확장 메서드 호출 식을 사용하여 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-143">You typically call extension methods using extension method invocation expressions.</span></span> <span data-ttu-id="b9ac6-144">정적 메서드 호출 구문을 사용하여 호출하는 경우는 드물지만 이 경우 클래스 이름을 추가하면 모호함이 해소됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-144">Adding the class name in the rare case where you call them using static method call syntax resolves ambiguity.</span></span>

<span data-ttu-id="b9ac6-145">`static using` 지시문은 모든 중첩 형식도 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-145">The `static using` directive also imports any nested types.</span></span> <span data-ttu-id="b9ac6-146">한정 없이 중첩 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-146">You can reference any nested types without qualification.</span></span>

## <a name="null-conditional-operators"></a><span data-ttu-id="b9ac6-147">Null 조건 연산자</span><span class="sxs-lookup"><span data-stu-id="b9ac6-147">Null-conditional operators</span></span>

<span data-ttu-id="b9ac6-148">*null 조건 연산자*를 사용하면 null 확인이 훨씬 더 쉽고 유연합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-148">The *null conditional operator* makes null checks much easier and fluid.</span></span> <span data-ttu-id="b9ac6-149">멤버 액세스 `.`를 `?.`로 바꾸세요.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-149">Replace the member access `.` with `?.`:</span></span>

[!code-csharp[NullConditional](../../../samples/snippets/csharp/new-in-6/program.cs#NullConditional)]

<span data-ttu-id="b9ac6-150">이전 예제에서 person 개체가 `null`인 경우 `first` 변수에 `null`이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-150">In the preceding example, the variable `first` is assigned `null` if the person object is `null`.</span></span> <span data-ttu-id="b9ac6-151">그렇지 않은 경우 `FirstName` 속성의 값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-151">Otherwise, it is assigned the value of the `FirstName` property.</span></span> <span data-ttu-id="b9ac6-152">가장 중요한 점은 `?.`는 `person` 변수가 `null`일 경우 이 코드 줄이 `NullReferenceException`을 생성하지 않음을 의미한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-152">Most importantly, the `?.` means that this line of code doesn't generate a `NullReferenceException` if the `person` variable is `null`.</span></span> <span data-ttu-id="b9ac6-153">대신 이 코드 줄은 단락되고 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-153">Instead, it short-circuits and returns `null`.</span></span> <span data-ttu-id="b9ac6-154">또한 배열 또는 인덱서 액세스에 null 조건 연산자를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-154">You can also use a null conditional operator for array or indexer access.</span></span> <span data-ttu-id="b9ac6-155">인덱스 식에서 `[]`를 `?[]`로 바꾸세요.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-155">Replace `[]` with `?[]` in the index expression.</span></span>

<span data-ttu-id="b9ac6-156">다음 식은 `person` 값에 관계없이 `string`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-156">The following expression returns a `string`, regardless of the value of `person`.</span></span> <span data-ttu-id="b9ac6-157">이 구문을 *null 결합* 연산자와 함께 사용하여 속성 중 하나가 `null`일 경우 기본값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-157">You often use this construct with the *null coalescing* operator to assign default values when one of the properties is `null`.</span></span> <span data-ttu-id="b9ac6-158">식이 단락되면 반환된 `null` 값은 전체 식과 일치하도록 형식화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-158">When the expression short-circuits, the `null` value returned is typed to match the full expression.</span></span>

[!code-csharp[NullCoalescing](../../../samples/snippets/csharp/new-in-6/program.cs#NullCoalescing)]

<span data-ttu-id="b9ac6-159">또한 `?.`를 사용하여 메서드를 조건부로 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-159">You can also use `?.` to conditionally invoke methods.</span></span> <span data-ttu-id="b9ac6-160">null 조건 연산자와 함께 멤버 함수를 사용하는 가장 일반적인 경우는 `null`일 수 있는 대리자(또는 이벤트 처리기)를 안전하게 호출하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-160">The most common use of member functions  with the null conditional operator is to safely invoke delegates (or event handlers) that may be `null`.</span></span>  <span data-ttu-id="b9ac6-161">`?.` 연산자를 통해 대리자의 `Invoke` 메서드를 호출하여 멤버에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-161">You'll call the delegate's `Invoke` method using the `?.` operator to access the member.</span></span> <span data-ttu-id="b9ac6-162">[대리자 패턴](../delegates-patterns.md#handling-null-delegates) 문서에서 예제를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-162">You can see an example in the [delegate patterns](../delegates-patterns.md#handling-null-delegates) article.</span></span>

<span data-ttu-id="b9ac6-163">`?.` 연산자 규칙을 적용하면 연산자의 왼쪽이 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-163">The rules of the `?.` operator ensure that the left-hand side of the operator is evaluated only once.</span></span> <span data-ttu-id="b9ac6-164">이렇게 하면 이벤트 처리기 사용 예제를 비롯한 많은 관용구를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-164">It enables many idioms, including the following example using event handlers:</span></span>

```csharp
// preferred in C# 6:
this.SomethingHappened?.Invoke(this, eventArgs);
```

<span data-ttu-id="b9ac6-165">또한 왼쪽이 한 번만 계산되도록 하면 `?.` 왼쪽에서 메서드 호출을 포함한 모든 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-165">Ensuring that the left side is evaluated only once also enables you to use any expression, including method calls, on the left side of the `?.`</span></span>

## <a name="string-interpolation"></a><span data-ttu-id="b9ac6-166">문자열 보간</span><span class="sxs-lookup"><span data-stu-id="b9ac6-166">String interpolation</span></span>

<span data-ttu-id="b9ac6-167">C# 6에서는 새 [문자열 보간](../language-reference/tokens/interpolated.md) 기능을 통해 문자열에 식을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-167">With C# 6, the new [string interpolation](../language-reference/tokens/interpolated.md) feature enables you to embed expressions in a string.</span></span> <span data-ttu-id="b9ac6-168">문자열 앞에 `$`를 추가하고 `{` 및 `}` 사이에 서수 대신 식을 사용하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-168">Simply preface the string with `$`and use expressions between `{` and `}` instead of ordinals:</span></span>

[!code-csharp[stringInterpolation](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

<span data-ttu-id="b9ac6-169">이 예제에서는 대체 식에 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-169">This example uses properties for the substituted expressions.</span></span> <span data-ttu-id="b9ac6-170">모든 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-170">You can use any expression.</span></span> <span data-ttu-id="b9ac6-171">예를 들어 보간의 일부로 학생의 성적 점수 평균을 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-171">For example, you could compute a student's grade point average as part of the interpolation:</span></span>

[!code-csharp[stringInterpolationFormat](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationFormat)]

<span data-ttu-id="b9ac6-172">이전 코드 줄은 소수 자릿수가 두 개인 부동 소수점 숫자로 `Grades.Average()` 값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-172">The preceding line of code formats the value for `Grades.Average()` as a floating-point number with two decimal places.</span></span>

<span data-ttu-id="b9ac6-173">일반적으로 특정 문화권을 사용하여 생성된 문자열의 서식을 지정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-173">Often, you may need to format the string produced using a specific culture.</span></span> <span data-ttu-id="b9ac6-174">문자열 보간에 의해 생성된 개체가 암시적으로 <xref:System.FormattableString?displayProperty=nameWithType>으로 변환될 수 있다는 사실을 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-174">You use the fact that the object produced by a string interpolation can be implicitly converted to <xref:System.FormattableString?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b9ac6-175"><xref:System.FormattableString> 인스턴스에는 복합 형식 문자열 및 문자열로 변환하기 전에 식을 계산한 결과가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-175">The <xref:System.FormattableString> instance contains the composite format string and the results of evaluating the expressions before converting them to strings.</span></span> <span data-ttu-id="b9ac6-176">문자열 형식을 지정할 때 <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> 메서드를 사용하여 문화권을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-176">Use the <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> method to specify the culture when formatting a string.</span></span> <span data-ttu-id="b9ac6-177">다음 예에서는 독일(de-DE) 문화권을 사용하여 문자열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-177">The following example produces a string using the German (de-DE) culture.</span></span> <span data-ttu-id="b9ac6-178">(기본적으로 독일 문화권은 ',' 문자를 소수 구분 기호로 사용하고 '.' 문자를 천 단위 구분 기호로 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="b9ac6-178">(By default, the German culture uses the ',' character for the decimal separator, and the '.' character as the thousands separator.)</span></span>

```csharp
FormattableString str = $"Average grade is {s.Grades.Average()}";
var gradeStr = str.ToString(new System.Globalization.CultureInfo("de-DE"));
```

<span data-ttu-id="b9ac6-179">문자열 보간을 시작하려면 [C#의 문자열 보간](../tutorials/exploration/interpolated-strings.yml) 대화형 자습서, [문자열 보간](../language-reference/tokens/interpolated.md) 문서 및 [C#의 문자열 보간](../tutorials/string-interpolation.md) 자습서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-179">To get started with string interpolation, see the [String interpolation in C#](../tutorials/exploration/interpolated-strings.yml) interactive tutorial, the [String interpolation](../language-reference/tokens/interpolated.md) article, and the [String interpolation in C#](../tutorials/string-interpolation.md) tutorial.</span></span>

## <a name="exception-filters"></a><span data-ttu-id="b9ac6-180">예외 필터</span><span class="sxs-lookup"><span data-stu-id="b9ac6-180">Exception filters</span></span>

<span data-ttu-id="b9ac6-181">*예외 필터*는 지정된 catch 절을 적용해야 하는 경우를 결정하는 절입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-181">*Exception Filters* are clauses that determine when a given catch clause should be applied.</span></span> <span data-ttu-id="b9ac6-182">예외 필터에 사용된 식이 `true`로 계산되면 catch 절은 예외에 대한 일반적인 처리를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-182">If the expression used for an exception filter evaluates to `true`, the catch clause performs its normal processing on an exception.</span></span> <span data-ttu-id="b9ac6-183">식이 `false`로 계산되면 `catch` 절을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-183">If the expression evaluates to `false`, then the `catch` clause is skipped.</span></span> <span data-ttu-id="b9ac6-184">한 가지 사용 예는 예외에 대한 정보를 검사하여 `catch` 절이 예외를 처리할 수 있는지 결정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-184">One use is to examine information about an exception to determine if a `catch` clause can process the exception:</span></span>

[!code-csharp[ExceptionFilter](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilter)]

## <a name="the-nameof-expression"></a><span data-ttu-id="b9ac6-185">`nameof` 식</span><span class="sxs-lookup"><span data-stu-id="b9ac6-185">The `nameof` expression</span></span>

<span data-ttu-id="b9ac6-186">[nameof](../language-reference/operators/nameof.md) 식은 기호 이름으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-186">The [nameof](../language-reference/operators/nameof.md) expression evaluates to the name of a symbol.</span></span> <span data-ttu-id="b9ac6-187">변수, 속성 또는 멤버 필드의 이름이 필요할 때마다 도구를 작동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-187">It's a great way to get tools working whenever you need the name of a variable, a property, or a member field.</span></span> <span data-ttu-id="b9ac6-188">`nameof`의 가장 일반적인 사용 예 중 하나는 예외를 일으킨 기호의 이름을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-188">One of the most common uses for `nameof` is to provide the name of a symbol that caused an exception:</span></span>

[!code-csharp[nameof](../../../samples/snippets/csharp/new-in-6/NewCode.cs#UsingStaticString)]

<span data-ttu-id="b9ac6-189">또 다른 사용 예는 `INotifyPropertyChanged` 인터페이스를 구현하는 XAML 기반 애플리케이션에서 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-189">Another use is with XAML-based applications that implement the `INotifyPropertyChanged` interface:</span></span>

[!code-csharp[nameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#nameofNotify)]

## <a name="await-in-catch-and-finally-blocks"></a><span data-ttu-id="b9ac6-190">Catch 및 Finally 블록의 Await</span><span class="sxs-lookup"><span data-stu-id="b9ac6-190">Await in Catch and Finally blocks</span></span>

<span data-ttu-id="b9ac6-191">C# 5에는 `await` 식을 배치할 수 있는 위치에 대한 여러 제한 사항이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-191">C# 5 had several limitations around where you could place `await` expressions.</span></span> <span data-ttu-id="b9ac6-192">이제 C# 6에서는 `catch` 또는 `finally` 식에서 `await`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-192">With C# 6, you can now use `await` in `catch` or `finally` expressions.</span></span> <span data-ttu-id="b9ac6-193">이 방법이 로깅 시나리오에서 가장 일반적을 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-193">This is most often used with logging scenarios:</span></span>

[!code-csharp[AwaitFinally](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#AwaitFinally)]

<span data-ttu-id="b9ac6-194">`catch` 및 `finally` 절 내부에 `await` 지원을 추가하기 위한 구현 세부 정보에 따라 동작이 동기 코드에 대한 동작과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-194">The implementation details for adding `await` support inside `catch` and `finally` clauses ensure that the behavior is consistent with the behavior for synchronous code.</span></span> <span data-ttu-id="b9ac6-195">`catch` 또는 `finally` 절에서 실행되는 코드가 throw되면 실행은 다음 바깥쪽 블록에서 적합한 `catch` 절을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-195">When code executed in a `catch` or `finally` clause throws, execution looks for a suitable `catch` clause in the next surrounding block.</span></span> <span data-ttu-id="b9ac6-196">현재 예외가 있는 경우 해당 예외가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-196">If there was a current exception, that exception is lost.</span></span> <span data-ttu-id="b9ac6-197">`catch` 및 `finally` 절에서 대기된 식에서도 같은 작업이 수행됩니다. 적합한 `catch`가 검색되고 현재 예외(있는 경우)가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-197">The same happens with awaited expressions in `catch` and `finally` clauses: a suitable `catch` is searched for, and the current exception, if any, is lost.</span></span>  

> [!NOTE]
> <span data-ttu-id="b9ac6-198">이 동작 때문에 새 예외가 추가되지 않도록 `catch` 및 `finally` 절을 신중하게 작성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-198">This behavior is the reason it's recommended to write `catch` and `finally` clauses carefully, to avoid introducing new exceptions.</span></span>

## <a name="initialize-associative-collections-using-indexers"></a><span data-ttu-id="b9ac6-199">인덱서를 사용하여 연결 컬렉션 초기화</span><span class="sxs-lookup"><span data-stu-id="b9ac6-199">Initialize associative collections using indexers</span></span>

<span data-ttu-id="b9ac6-200">*인덱스 이니셜라이저*는 컬렉션 이니셜라이저를 인덱스 사용과 더 일관되도록 하는 두 가지 기능 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-200">*Index Initializers* is one of two features that make collection initializers more consistent with index usage.</span></span> <span data-ttu-id="b9ac6-201">C#의 이전 릴리스에서는 키 및 값 쌍을 중괄호로 묶어 <xref:System.Collections.Generic.Dictionary%602>를 포함하여 시퀀스 스타일 컬렉션에서 *컬렉션 이니셜라이저*를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-201">In earlier releases of C#, you could use *collection initializers* with sequence style collections, including <xref:System.Collections.Generic.Dictionary%602>, by adding braces around key and value pairs:</span></span>

[!code-csharp[ListInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#CollectionInitializer)]

<span data-ttu-id="b9ac6-202"><xref:System.Collections.Generic.Dictionary%602> 컬렉션 및 액세스 가능한 `Add` 메서드가 둘 이상의 인수를 허용하는 다른 형식에서 이를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-202">You can use them with <xref:System.Collections.Generic.Dictionary%602> collections and other types where the accessible `Add` method accepts more than one argument.</span></span> <span data-ttu-id="b9ac6-203">새로운 구문은 컬렉션에 인덱스를 사용하여 할당을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-203">The new syntax supports assignment using an index into the collection:</span></span>

[!code-csharp[DictionaryInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#DictionaryInitializer)]

<span data-ttu-id="b9ac6-204">이 기능은 여러 버전에 대한 시퀀스 컨테이너를 대신한 것과 비슷한 구문을 사용하여 연관 컨테이너를 초기화할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-204">This feature means that associative containers can be initialized using syntax similar to what's been in place for sequence containers for several versions.</span></span>

## <a name="extension-add-methods-in-collection-initializers"></a><span data-ttu-id="b9ac6-205">컬렉션 이니셜라이저의 확장 `Add` 메서드</span><span class="sxs-lookup"><span data-stu-id="b9ac6-205">Extension `Add` methods in collection initializers</span></span>

<span data-ttu-id="b9ac6-206">컬렉션을 더 쉽게 초기화하도록 하는 또 다른 기능은 `Add` 메서드에 *확장 메서드*를 사용하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-206">Another feature that makes collection initialization easier is the ability to use an *extension method* for the `Add` method.</span></span> <span data-ttu-id="b9ac6-207">이 기능은 Visual Basic의 패리티를 위해 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-207">This feature was added for parity with Visual Basic.</span></span> <span data-ttu-id="b9ac6-208">이 기능은 의미상으로 새 항목을 추가하기 위해 다른 이름을 가진 메서드가 포함된 사용자 지정 컬렉션 클래스가 있는 경우 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-208">The feature is most useful when you have a custom collection class that has a method with a different name to semantically add new items.</span></span>

## <a name="improved-overload-resolution"></a><span data-ttu-id="b9ac6-209">향상된 오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="b9ac6-209">Improved overload resolution</span></span>

<span data-ttu-id="b9ac6-210">이 마지막 기능은 알지 못하는 기능일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-210">This last feature is one you probably won't notice.</span></span> <span data-ttu-id="b9ac6-211">C# 컴파일러의 이전 버전에서 람다 식을 포함하는 일부 메서드 호출이 모호한 것으로 확인될 수 있는 구문이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-211">There were constructs where the previous version of the C# compiler may have found some method calls involving lambda expressions ambiguous.</span></span> <span data-ttu-id="b9ac6-212">이 메서드를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-212">Consider this method:</span></span>

[!code-csharp[AsyncMethod](../../../samples/snippets/csharp/new-in-6/overloads.cs#AsyncMethod)]

<span data-ttu-id="b9ac6-213">C#의 이전 버전에서는 메서드 그룹 구문을 통한 해당 메서드 호출이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-213">In earlier versions of C#, calling that method using the method group syntax would fail:</span></span>

[!code-csharp[MethodGroup](../../../samples/snippets/csharp/new-in-6/overloads.cs#MethodGroup)]

<span data-ttu-id="b9ac6-214">이전 컴파일러에서는 `Task.Run(Action)` 및 `Task.Run(Func<Task>())`를 제대로 구분할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-214">The earlier compiler couldn't distinguish correctly between `Task.Run(Action)` and `Task.Run(Func<Task>())`.</span></span> <span data-ttu-id="b9ac6-215">이전 버전에서는 람다 식을 인수로 사용해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-215">In previous versions, you'd need to use a lambda expression as an argument:</span></span>

[!code-csharp[Lambda](../../../samples/snippets/csharp/new-in-6/overloads.cs#Lambda)]

<span data-ttu-id="b9ac6-216">C# 6 컴파일러에서는 `Task.Run(Func<Task>())`가 더 나은 선택인지 제대로 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-216">The C# 6 compiler correctly determines that `Task.Run(Func<Task>())` is a better choice.</span></span>

### <a name="deterministic-compiler-output"></a><span data-ttu-id="b9ac6-217">deterministic 컴파일러 출력</span><span class="sxs-lookup"><span data-stu-id="b9ac6-217">Deterministic compiler output</span></span>

<span data-ttu-id="b9ac6-218">`-deterministic` 옵션은 컴파일러가 동일한 원본 파일의 연속적인 컴파일을 위해 바이트 단위의 동일한 출력 어셈블리를 생성하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-218">The `-deterministic` option instructs the compiler to produce a byte-for-byte identical output assembly for successive compilations of the same source files.</span></span>

<span data-ttu-id="b9ac6-219">기본적으로 컴파일이 실행될 때마다 고유한 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-219">By default, every compilation produces unique output on each compilation.</span></span> <span data-ttu-id="b9ac6-220">컴파일러는 임의의 숫자에서 생성된 GUID와 타임스탬프를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-220">The compiler adds a timestamp, and a GUID generated from random numbers.</span></span> <span data-ttu-id="b9ac6-221">바이트별 출력을 비교하여 빌드 간 일관성을 유지하려면 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-221">You use this option if you want to compare the byte-for-byte output to ensure consistency across builds.</span></span>

<span data-ttu-id="b9ac6-222">자세한 내용은 [-deterministic 컴파일러 옵션](../language-reference/compiler-options/deterministic-compiler-option.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9ac6-222">For more information, see the [-deterministic compiler option](../language-reference/compiler-options/deterministic-compiler-option.md) article.</span></span>
