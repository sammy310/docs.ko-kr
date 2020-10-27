---
title: 기본 제공 참조 형식 - C# 참조
description: 선언하는 데 사용할 수 있는 C# 키워드가 있는 참조 형식에 대해 알아봅니다.
ms.date: 06/25/2019
f1_keywords:
- object_CSharpKeyword
- object
- delegate_CSharpKeyword
- delegate
- dynamic_CSharpKeyword
- string
- string_CSharpKeyword
helpviewer_keywords:
- object keyword [C#]
- delegate keyword [C#]
- function pointers [C#]
- dynamic [C#]
- dynamic keyword [C#]
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.openlocfilehash: c2c03f47babd9ccf87eb60d33b9d65d1a9c82e2e
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223518"
---
# <a name="built-in-reference-types-c-reference"></a><span data-ttu-id="f55a9-103">기본 제공 참조 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f55a9-103">Built-in reference types (C# reference)</span></span>

<span data-ttu-id="f55a9-104">C#에는 여러 가지 기본 제공 참조 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-104">C# has a number of built-in reference types.</span></span> <span data-ttu-id="f55a9-105">.NET 라이브러리의 형식에 대한 동의어인 키워드 또는 연산자를 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-105">They have keywords or operators that are synonyms for a type in the .NET library.</span></span>

## <a name="the-object-type"></a><span data-ttu-id="f55a9-106">개체 유형</span><span class="sxs-lookup"><span data-stu-id="f55a9-106">The object type</span></span>

<span data-ttu-id="f55a9-107">`object` 형식은 .NET에서 <xref:System.Object?displayProperty=nameWithType>의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-107">The `object` type is an alias for <xref:System.Object?displayProperty=nameWithType> in .NET.</span></span> <span data-ttu-id="f55a9-108">C#의 통합 형식 시스템에서 모든 형식(사전 정의되거나 사용자 정의된 형식, 참조 형식, 값 형식)은 <xref:System.Object?displayProperty=nameWithType>에서 직접 또는 간접적으로 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-108">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f55a9-109">`object` 형식의 변수에 모든 형식의 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-109">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="f55a9-110">모든 `object` 변수는 리터럴 `null`을 사용하여 기본값으로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-110">Any `object` variable can be assigned to its default value using the literal `null`.</span></span> <span data-ttu-id="f55a9-111">값 형식의 변수가 개체로 변환된 경우 *boxed* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-111">When a variable of a value type is converted to object, it is said to be *boxed* .</span></span> <span data-ttu-id="f55a9-112">형식 `object`의 변수가 값 형식으로 변환된 경우 *unboxed* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-112">When a variable of type `object` is converted to a value type, it is said to be *unboxed* .</span></span> <span data-ttu-id="f55a9-113">자세한 내용은 [boxing 및 unboxing](../../programming-guide/types/boxing-and-unboxing.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55a9-113">For more information, see [Boxing and Unboxing](../../programming-guide/types/boxing-and-unboxing.md).</span></span>

## <a name="the-string-type"></a><span data-ttu-id="f55a9-114">문자열 유형</span><span class="sxs-lookup"><span data-stu-id="f55a9-114">The string type</span></span>

<span data-ttu-id="f55a9-115">`string` 형식은 0자 이상의 유니코드 문자 시퀀스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-115">The `string` type represents a sequence of zero or more Unicode characters.</span></span> <span data-ttu-id="f55a9-116">`string`는 .NET에서 <xref:System.String?displayProperty=nameWithType>의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-116">`string` is an alias for <xref:System.String?displayProperty=nameWithType> in .NET.</span></span>

<span data-ttu-id="f55a9-117">`string`은 참조 형식이지만 [같음 연산자 `==` 및 `!=`](../operators/equality-operators.md#string-equality)는 참조가 아니라 `string` 개체의 값을 비교하도록 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-117">Although `string` is a reference type, the [equality operators `==` and `!=`](../operators/equality-operators.md#string-equality) are defined to compare the values of `string` objects, not references.</span></span> <span data-ttu-id="f55a9-118">이 때문에 좀 더 직관적으로 문자열이 같은지 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-118">This makes testing for string equality more intuitive.</span></span> <span data-ttu-id="f55a9-119">예:</span><span class="sxs-lookup"><span data-stu-id="f55a9-119">For example:</span></span>

```csharp-interactive
string a = "hello";
string b = "h";
// Append to contents of 'b'
b += "ello";
Console.WriteLine(a == b);
Console.WriteLine(object.ReferenceEquals(a, b));
```

<span data-ttu-id="f55a9-120">이 코드는 "True"를 표시한 다음 "False"를 표시하며, 이는 문자열의 내용이 동일하지만 `a`와 `b`는 동일한 문자열 인스턴스를 가리키지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-120">This displays "True" and then "False" because the content of the strings are equivalent, but `a` and `b` do not refer to the same string instance.</span></span>

<span data-ttu-id="f55a9-121">[+ 연산자](../operators/addition-operator.md#string-concatenation)는 문자열을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-121">The [+ operator](../operators/addition-operator.md#string-concatenation) concatenates strings:</span></span>

```csharp
string a = "good " + "morning";
```

<span data-ttu-id="f55a9-122">이 경우 "good morning"이 포함된 문자열 개체가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-122">This creates a string object that contains "good morning".</span></span>

<span data-ttu-id="f55a9-123">문자열은 *변경할 수 없습니다* . 구문상 가능한 것처럼 보여도 개체를 만든 후에는 문자열 개체의 내용을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-123">Strings are *immutable* --the contents of a string object cannot be changed after the object is created, although the syntax makes it appear as if you can do this.</span></span> <span data-ttu-id="f55a9-124">예를 들어 이 코드를 작성하면 컴파일러는 실제로 새 문자 시퀀스를 보유할 새 문자열 개체를 만들고, 새 개체가 `b`에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-124">For example, when you write this code, the compiler actually creates a new string object to hold the new sequence of characters, and that new object is assigned to `b`.</span></span> <span data-ttu-id="f55a9-125">`b`에 할당된 메모리(문자열 "h"가 포함된 경우)는 가비지 수집에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-125">The memory that had been allocated for `b` (when it contained the string "h") is then eligible for garbage collection.</span></span>

```csharp
string b = "h";
b += "ello";
```

<span data-ttu-id="f55a9-126">`[]` [연산자](../operators/member-access-operators.md#indexer-operator-)는 문자열의 개별 문자에 대한 읽기 전용 액세스에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-126">The `[]` [operator](../operators/member-access-operators.md#indexer-operator-) can be used for readonly access to individual characters of a string.</span></span> <span data-ttu-id="f55a9-127">유효한 인덱스는 `0`에서 시작되고 문자열의 길이보다 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-127">Valid index values start at `0` and must be less than the length of the string:</span></span>

```csharp
string str = "test";
char x = str[2];  // x = 's';
```

<span data-ttu-id="f55a9-128">비슷한 방식으로 `[]` 연산자도 문자열의 각 문자를 반복하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-128">In similar fashion, the `[]` operator can also be used for iterating over each character in a string:</span></span>

```csharp-interactive
string str = "test";

for (int i = 0; i < str.Length; i++)
{
  Console.Write(str[i] + " ");
}
// Output: t e s t
```

<span data-ttu-id="f55a9-129">문자열 리터럴은 `string` 형식이며, quoted 및 `@`-quoted의 두 가지 형식으로 작성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-129">String literals are of type `string` and can be written in two forms, quoted and `@`-quoted.</span></span> <span data-ttu-id="f55a9-130">따옴표가 있는 문자열 리터럴은 큰따옴표(")로 묶여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-130">Quoted string literals are enclosed in double quotation marks ("):</span></span>

```csharp
"good morning"  // a string literal
```

<span data-ttu-id="f55a9-131">문자열 리터럴에는 모든 문자 리터럴이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-131">String literals can contain any character literal.</span></span> <span data-ttu-id="f55a9-132">이스케이프 시퀀스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-132">Escape sequences are included.</span></span> <span data-ttu-id="f55a9-133">다음 예제에서는 이스케이프 시퀀스 `\\`를 백슬래시에 사용하고, `\u0066`을 f에 사용하고, `\n`을 줄 바꿈에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-133">The following example uses escape sequence `\\` for backslash, `\u0066` for the letter f, and `\n` for newline.</span></span>

```csharp-interactive
string a = "\\\u0066\n F";
Console.WriteLine(a);
// Output:
// \f
//  F
```

> [!NOTE]
> <span data-ttu-id="f55a9-134">이스케이프 코드 `\udddd`(여기서 `dddd`는 4자리 숫자)는 유니코드 문자 U+`dddd`를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-134">The escape code `\udddd` (where `dddd` is a four-digit number) represents the Unicode character U+`dddd`.</span></span> <span data-ttu-id="f55a9-135">8자리 유니코드 이스케이프 코드 `\Udddddddd`도 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-135">Eight-digit Unicode escape codes are also recognized: `\Udddddddd`.</span></span>

<span data-ttu-id="f55a9-136">[축자 문자열 리터럴](../tokens/verbatim.md)은 `@`로 시작하며 큰따옴표로 묶여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-136">[Verbatim string literals](../tokens/verbatim.md) start with `@` and are also enclosed in double quotation marks.</span></span> <span data-ttu-id="f55a9-137">예:</span><span class="sxs-lookup"><span data-stu-id="f55a9-137">For example:</span></span>

```csharp
@"good morning"  // a string literal
```

<span data-ttu-id="f55a9-138">축자 문자열의 장점은 이스케이프 시퀀스가 처리되지 *않으므로* , 정규화된 Windows 파일 이름 등을 쉽게 쓸 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-138">The advantage of verbatim strings is that escape sequences are *not* processed, which makes it easy to write, for example, a fully qualified Windows file name:</span></span>

```csharp
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"
```

<span data-ttu-id="f55a9-139">@-quoted 문자열에 큰따옴표를 포함하려면 큰따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-139">To include a double quotation mark in an @-quoted string, double it:</span></span>

```csharp
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.
```

## <a name="the-delegate-type"></a><span data-ttu-id="f55a9-140">대리자 형식</span><span class="sxs-lookup"><span data-stu-id="f55a9-140">The delegate type</span></span>

<span data-ttu-id="f55a9-141">delegate 형식의 선언은 메서드 시그니처와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-141">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="f55a9-142">반환 값이 있으며 모든 형식의 매개 변수를 개수에 관계없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-142">It has a return value and any number of parameters of any type:</span></span>

```csharp
public delegate void MessageDelegate(string message);
public delegate int AnotherDelegate(MyType m, long num);
```

<span data-ttu-id="f55a9-143">.NET에서 `System.Action` 및 `System.Func` 유형은 많은 일반 대리자에 대한 일반적인 정의를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-143">In .NET, `System.Action` and `System.Func` types provide generic definitions for many common delegates.</span></span> <span data-ttu-id="f55a9-144">새 사용자 지정 대리자 형식을 정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-144">You likely don't need to define new custom delegate types.</span></span> <span data-ttu-id="f55a9-145">대신 제공된 제네릭 형식의 인스턴스화를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-145">Instead, you can create instantiations of the provided generic types.</span></span>

<span data-ttu-id="f55a9-146">`delegate`는 명명된 메서드나 무명 메서드를 캡슐화하는 데 사용할 수 있는 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-146">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="f55a9-147">대리자는 C++의 함수 포인터와 비슷하지만 형식 안전성과 보안성을 제공한다는 점이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-147">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="f55a9-148">대리자 적용에 대해서는 [대리자](../../programming-guide/delegates/index.md) 및 [제네릭 대리자](../../programming-guide/generics/generic-delegates.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55a9-148">For applications of delegates, see [Delegates](../../programming-guide/delegates/index.md) and [Generic Delegates](../../programming-guide/generics/generic-delegates.md).</span></span> <span data-ttu-id="f55a9-149">대리자는 [이벤트](../../programming-guide/events/index.md)의 기반이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-149">Delegates are the basis for [Events](../../programming-guide/events/index.md).</span></span> <span data-ttu-id="f55a9-150">대리자는 명명된 메서드나 무명 메서드와 연결하여 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-150">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span>

<span data-ttu-id="f55a9-151">대리자는 호환되는 반환 형식 및 입력 매개 변수가 있는 메서드나 람다 식을 사용하여 인스턴스화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-151">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="f55a9-152">메서드 시그니처에서 허용되는 가변성 수준에 대한 자세한 내용은 [대리자의 가변성](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55a9-152">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span> <span data-ttu-id="f55a9-153">무명 메서드에서 사용하기 위해 메서드에 연결할 대리자와 코드를 함께 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-153">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span>

## <a name="the-dynamic-type"></a><span data-ttu-id="f55a9-154">동적 형식</span><span class="sxs-lookup"><span data-stu-id="f55a9-154">The dynamic type</span></span>

<span data-ttu-id="f55a9-155">`dynamic` 유형은 변수 및 해당 멤버에 대한 참조 사용이 컴파일 파일 형식 검사를 바이패스함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-155">The `dynamic` type indicates that use of the variable and references to its members bypass compile-time type checking.</span></span> <span data-ttu-id="f55a9-156">대신, 이러한 작업은 런타임에 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-156">Instead, these operations are resolved at run time.</span></span> <span data-ttu-id="f55a9-157">`dynamic` 형식은 Office Automation API와 같은 COM API, IronPython 라이브러리 등의 동적 API 및 HTML DOM(문서 개체 모델)에 대한 액세스를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-157">The `dynamic` type simplifies access to COM APIs such as the Office Automation APIs, to dynamic APIs such as IronPython libraries, and to the HTML Document Object Model (DOM).</span></span>

<span data-ttu-id="f55a9-158">`dynamic` 형식은 대부분의 상황에서 `object` 형식처럼 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-158">Type `dynamic` behaves like type `object` in most circumstances.</span></span> <span data-ttu-id="f55a9-159">특히 null이 아닌 모든 식은 `dynamic` 형식으로 변환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-159">In particular, any non-null expression can be converted to the `dynamic` type.</span></span> <span data-ttu-id="f55a9-160">`dynamic` 유형의 식을 포함하는 작업은 컴파일러에서 확인되거나 형식이 검사되지 않았다는 점에서 `dynamic` 유형은 `object`와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-160">The `dynamic` type differs from `object` in that operations that contain expressions of type `dynamic` are not resolved or type checked by the compiler.</span></span> <span data-ttu-id="f55a9-161">컴파일러는 작업에 대한 정보를 패키지하며, 나중에 해당 정보는 런타임에 작업을 평가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-161">The compiler packages together information about the operation, and that information is later used to evaluate the operation at run time.</span></span> <span data-ttu-id="f55a9-162">이 과정에서 `dynamic` 형식의 변수는 `object` 형식의 변수로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-162">As part of the process, variables of type `dynamic` are compiled into variables of type `object`.</span></span> <span data-ttu-id="f55a9-163">따라서 `dynamic` 형식은 컴파일 시간에만 존재하고 런타임에는 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-163">Therefore, type `dynamic` exists only at compile time, not at run time.</span></span>

<span data-ttu-id="f55a9-164">다음 예제에서는 `dynamic` 형식의 변수와 `object` 형식의 변수를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-164">The following example contrasts a variable of type `dynamic` to a variable of type `object`.</span></span> <span data-ttu-id="f55a9-165">컴파일 시간에 각 변수의 형식을 확인하려면 `WriteLine` 문의 `dyn` 또는 `obj` 위에 마우스 포인터를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-165">To verify the type of each variable at compile time, place the mouse pointer over `dyn` or `obj` in the `WriteLine` statements.</span></span> <span data-ttu-id="f55a9-166">IntelliSense를 사용할 수 있는 편집기로 다음 코드를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-166">Copy the following code into an editor where IntelliSense is available.</span></span> <span data-ttu-id="f55a9-167">IntelliSense는 `dyn`에 대해 **dynamic** 을 표시하고 `obj`에 대해 **object** 를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-167">IntelliSense shows **dynamic** for `dyn` and **object** for `obj`.</span></span>

[!code-csharp[csrefKeywordsTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#21)]

<span data-ttu-id="f55a9-168"><xref:System.Console.WriteLine%2A> 문은 `dyn` 및 `obj`의 런타임 형식을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-168">The <xref:System.Console.WriteLine%2A> statements display the run-time types of `dyn` and `obj`.</span></span> <span data-ttu-id="f55a9-169">이 시점에는 둘 다 동일한 형식인 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-169">At that point, both have the same type, integer.</span></span> <span data-ttu-id="f55a9-170">다음 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-170">The following output is produced:</span></span>

```console
System.Int32
System.Int32
```

<span data-ttu-id="f55a9-171">컴파일 시간에 `dyn` 및 `obj` 간의 차이를 보려면 앞의 예제에서 선언과 `WriteLine` 문 사이에 다음 두 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-171">To see the difference between `dyn` and `obj` at compile time, add the following two lines between the declarations and the `WriteLine` statements in the previous example.</span></span>

```csharp
dyn = dyn + 3;
obj = obj + 3;
```

 <span data-ttu-id="f55a9-172">`obj + 3` 식에 정수와 개체를 추가하려는 시도와 관련해서 컴파일러 오류가 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-172">A compiler error is reported for the attempted addition of an integer and an object in expression `obj + 3`.</span></span> <span data-ttu-id="f55a9-173">하지만 `dyn + 3`에 대한 오류는 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-173">However, no error is reported for `dyn + 3`.</span></span> <span data-ttu-id="f55a9-174">`dyn`의 형식이 `dynamic`이기 때문에 `dyn`을 포함하는 식은 컴파일 시간에 확인되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-174">The expression that contains `dyn` is not checked at compile time because the type of `dyn` is `dynamic`.</span></span>

<span data-ttu-id="f55a9-175">다음 예제에서는 여러 선언에 `dynamic`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-175">The following example uses `dynamic` in several declarations.</span></span> <span data-ttu-id="f55a9-176">또한 `Main` 메서드는 컴파일 시간 형식 검사를 런타임 형식 검사와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="f55a9-176">The `Main` method also contrasts compile-time type checking with run-time type checking.</span></span>

[!code-csharp[csrefKeywordsTypes#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic2.cs#25)]

### <a name="see-also"></a><span data-ttu-id="f55a9-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f55a9-177">See also</span></span>

- [<span data-ttu-id="f55a9-178">C# 참조</span><span class="sxs-lookup"><span data-stu-id="f55a9-178">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f55a9-179">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="f55a9-179">C# Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="f55a9-180">이벤트</span><span class="sxs-lookup"><span data-stu-id="f55a9-180">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="f55a9-181">dynamic 형식 사용</span><span class="sxs-lookup"><span data-stu-id="f55a9-181">Using Type dynamic</span></span>](../../programming-guide/types/using-type-dynamic.md)
- [<span data-ttu-id="f55a9-182">문자열 사용에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="f55a9-182">Best Practices for Using Strings</span></span>](../../../standard/base-types/best-practices-strings.md)
- [<span data-ttu-id="f55a9-183">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="f55a9-183">Basic String Operations</span></span>](../../../standard/base-types/basic-string-operations.md)
- [<span data-ttu-id="f55a9-184">새 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="f55a9-184">Creating New Strings</span></span>](../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="f55a9-185">형식 테스트 및 캐스트 연산자</span><span class="sxs-lookup"><span data-stu-id="f55a9-185">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
- [<span data-ttu-id="f55a9-186">패턴 일치, as 및 is 연산자를 사용하여 안전하게 캐스트하는 방법</span><span class="sxs-lookup"><span data-stu-id="f55a9-186">How to safely cast using pattern matching and the as and is operators</span></span>](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [<span data-ttu-id="f55a9-187">연습: 동적 개체 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="f55a9-187">Walkthrough: creating and using dynamic objects</span></span>](../../programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- <xref:System.Object?displayProperty=nameWithType>
- <xref:System.String?displayProperty=nameWithType>
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>
