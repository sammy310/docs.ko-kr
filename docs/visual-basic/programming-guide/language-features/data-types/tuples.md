---
description: '다음에 대 한 자세한 정보: 튜플 (Visual Basic)'
title: 튜플
ms.date: 04/23/2017
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
ms.openlocfilehash: f598facb446b7d50864c0cf9151195cfcde158bb
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100454458"
---
# <a name="tuples-visual-basic"></a><span data-ttu-id="109c5-103">튜플(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="109c5-103">Tuples (Visual Basic)</span></span>

<span data-ttu-id="109c5-104">Visual Basic 2017부터 Visual Basic 언어는 튜플을 만들고 튜플 요소에 더 쉽게 액세스할 수 있도록 하는 튜플에 대 한 기본 제공 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-104">Starting with Visual Basic 2017, the Visual Basic language offers built-in support for tuples that makes creating tuples and accessing the elements of tuples easier.</span></span> <span data-ttu-id="109c5-105">튜플은 값의 특정 개수와 시퀀스를 포함 하는 간단한 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-105">A tuple is a lightweight data structure that has a specific number and sequence of values.</span></span> <span data-ttu-id="109c5-106">튜플을 인스턴스화할 때 각 값 (또는 요소)의 숫자와 데이터 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-106">When you instantiate the tuple, you define the number and the data type of each value (or element).</span></span> <span data-ttu-id="109c5-107">예를 들어 2 튜플 (또는 쌍)에는 두 개의 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-107">For example, a 2-tuple (or pair) has two elements.</span></span> <span data-ttu-id="109c5-108">첫 번째 `Boolean` 값은 값이 고, 두 번째는 일 수 있습니다 `String` .</span><span class="sxs-lookup"><span data-stu-id="109c5-108">The first might be a `Boolean` value, while the second is a `String`.</span></span> <span data-ttu-id="109c5-109">튜플을 사용 하면 여러 값을 단일 개체에 쉽게 저장할 수 있으므로 일반적으로 메서드에서 여러 값을 반환 하는 간단한 방법으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-109">Because tuples make it easy to store multiple values in a single object, they are often used as a lightweight way to return multiple values from a method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="109c5-110">튜플을 지원 하려면 <xref:System.ValueTuple> 형식이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-110">Tuple support requires the <xref:System.ValueTuple> type.</span></span> <span data-ttu-id="109c5-111">.NET Framework 4.7가 설치 되지 않은 경우 nuget `System.ValueTuple` 갤러리에서 사용할 수 있는 nuget 패키지를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-111">If the .NET Framework 4.7 is not installed, you must add the NuGet package `System.ValueTuple`, which is available on the NuGet Gallery.</span></span> <span data-ttu-id="109c5-112">이 패키지가 없으면 "미리 정의 된 유형 ' System.valuetuple (Of,,,) '이 (가) 정의 되지 않았거나 가져오지 않았습니다."와 유사한 컴파일 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-112">Without this package, you may get a compilation error similar to, "Predefined type 'ValueTuple(Of,,,)' is not defined or imported."</span></span>

## <a name="instantiating-and-using-a-tuple"></a><span data-ttu-id="109c5-113">튜플 인스턴스화 및 사용</span><span class="sxs-lookup"><span data-stu-id="109c5-113">Instantiating and using a tuple</span></span>

<span data-ttu-id="109c5-114">쉼표로 구분 된 값을 괄호로 묶어 튜플을 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-114">You instantiate a tuple by enclosing its comma-delimited values in parentheses.</span></span> <span data-ttu-id="109c5-115">이러한 각 값은 튜플의 필드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-115">Each of those values then becomes a field of the tuple.</span></span> <span data-ttu-id="109c5-116">예를 들어, 다음 코드는을 `Date` 첫 번째 값으로,를 두 번째 값으로,를 세 번째 값으로 사용 하 여 삼중 (또는 3 튜플)을 정의 합니다 `String` `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="109c5-116">For example, the following code defines a triple (or 3-tuple) with a `Date` as its first value, a `String` as its second, and a `Boolean` as its third.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

<span data-ttu-id="109c5-117">기본적으로 튜플의 각 필드 이름은 `Item` 튜플의 필드의 1부터 시작 하는 위치와 함께 문자열로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-117">By default, the name of each field in a tuple consists of the string `Item` along with the field's one-based position in the tuple.</span></span> <span data-ttu-id="109c5-118">이 3 튜플의 필드는이 고, 필드는 이며 `Date` `Item1` `String` `Item2` , `Boolean` 필드는 `Item3` 입니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-118">For this 3-tuple, the `Date` field is `Item1`, the `String` field is `Item2`, and the `Boolean` field is `Item3`.</span></span> <span data-ttu-id="109c5-119">다음 예제에서는 이전 코드 줄에서 인스턴스화된 튜플의 필드 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-119">The following example displays the values of fields of the tuple instantiated in the previous line of code</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

<span data-ttu-id="109c5-120">Visual Basic 튜플의 필드는 읽기/쓰기입니다. 튜플을 인스턴스화한 후에는 해당 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-120">The fields of a Visual Basic tuple are read-write; after you've instantiated a tuple, you can modify its values.</span></span> <span data-ttu-id="109c5-121">다음 예제에서는 이전 예제에서 만든 튜플의 세 필드 중 두 개를 수정 하 고 결과를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-121">The following example modifies two of the three fields of the tuple created in the previous example and displays the result.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a><span data-ttu-id="109c5-122">명명 된 튜플 인스턴스화 및 사용</span><span class="sxs-lookup"><span data-stu-id="109c5-122">Instantiating and using a named tuple</span></span>

<span data-ttu-id="109c5-123">튜플의 필드에 대해 기본 이름을 사용 하는 대신 튜플의 요소에 고유한 이름을 할당 하 여 *명명 된 튜플을* 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-123">Rather than using default names for a tuple's fields, you can instantiate a *named tuple* by assigning your own names to the tuple's elements.</span></span> <span data-ttu-id="109c5-124">그러면 지정 된 이름이 *나* 기본 이름으로 튜플의 필드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-124">The tuple's fields can then be accessed by their assigned names *or* by their default names.</span></span> <span data-ttu-id="109c5-125">다음 예제에서는 첫 번째 필드 `EventDate` , 두 번째 및 세 번째 필드의 이름을 명시적으로 지정할 때를 제외 하 고 이전 처럼 동일한 3 튜플을 인스턴스화합니다 `Name` `IsHoliday` .</span><span class="sxs-lookup"><span data-stu-id="109c5-125">The following example instantiates the same 3-tuple as previously, except that it explicitly names the first field `EventDate`, the second `Name`, and the third `IsHoliday`.</span></span> <span data-ttu-id="109c5-126">그런 다음 필드 값을 표시 하 고 수정 하 고 필드 값을 다시 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-126">It then displays the field values, modifies them, and displays the field values again.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="109c5-127">유추된 튜플 요소 이름</span><span class="sxs-lookup"><span data-stu-id="109c5-127">Inferred tuple element names</span></span>

<span data-ttu-id="109c5-128">Visual Basic 15.3부터 Visual Basic 튜플 요소의 이름을 유추할 수 있습니다. 명시적으로 할당할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-128">Starting with Visual Basic 15.3, Visual Basic can infer the names of tuple elements; you do not have to assign them explicitly.</span></span> <span data-ttu-id="109c5-129">유추 된 튜플 이름은 변수 집합에서 튜플을 초기화 하 고 튜플 요소 이름이 변수 이름과 동일 하 게 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-129">Inferred tuple names are useful when you initialize a tuple from a set of variables, and you want the tuple element name to be the same as the variable name.</span></span>

<span data-ttu-id="109c5-130">다음 예에서는 명시적으로 `stateInfo` 명명 된 세 요소인, 및가 포함 된 튜플을 만듭니다 `state` `stateName` `capital` .</span><span class="sxs-lookup"><span data-stu-id="109c5-130">The following example creates a `stateInfo` tuple that contains three explicitly named elements, `state`, `stateName`, and `capital`.</span></span> <span data-ttu-id="109c5-131">요소 이름을 지정 하는 경우 튜플 초기화 문은 명명 된 요소에 동일한 이름의 변수 값을 할당 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-131">Note that, in naming the elements, the tuple initialization statement simply assigns the named elements the values of the identically named variables.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]

<span data-ttu-id="109c5-132">요소와 변수는 이름이 동일 하기 때문에 Visual Basic 컴파일러는 다음 예제와 같이 필드의 이름을 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-132">Because elements and variables have the same name, the Visual Basic compiler can infer the names of the fields, as the following example shows.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

<span data-ttu-id="109c5-133">유추 된 튜플 요소 이름을 사용 하려면 Visual Basic 프로젝트 (.vbproj) 파일에서 사용할 Visual Basic 컴파일러의 버전을 정의 해야 합니다 \* .</span><span class="sxs-lookup"><span data-stu-id="109c5-133">To enable inferred tuple element names, you must define the version of the Visual Basic compiler to use in your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.3</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="109c5-134">버전 번호는 15.3부터 시작 하는 Visual Basic 컴파일러의 모든 버전이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-134">The version number can be any version of the Visual Basic compiler starting with 15.3.</span></span> <span data-ttu-id="109c5-135">특정 컴파일러 버전을 하드 코딩 하는 대신의 값으로 "최신"을 지정 `LangVersion` 하 여 시스템에 설치 된 Visual Basic 컴파일러의 최신 버전으로 컴파일할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-135">Rather than hard-coding a specific compiler version, you can also specify "Latest" as the value of `LangVersion` to compile with the most recent version of the Visual Basic compiler installed on your system.</span></span>

<span data-ttu-id="109c5-136">자세한 내용은 [Visual Basic 언어 버전 설정](../../../language-reference/configure-language-version.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="109c5-136">For more information, see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

<span data-ttu-id="109c5-137">경우에 따라 Visual Basic 컴파일러는 후보 이름에서 튜플 요소 이름을 유추할 수 없으며 튜플 필드는, 등의 기본 이름을 사용해 서만 참조할 수 있습니다 `Item1` `Item2` . 여기에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-137">In some cases, the Visual Basic compiler cannot infer the tuple element name from the candidate name, and the tuple field can only be referenced using its default name, such as `Item1`, `Item2`, etc. These include:</span></span>

- <span data-ttu-id="109c5-138">후보 이름은 튜플 멤버의 이름 (예:, 또는)과 동일 합니다 `Item3` `Rest` `ToString` .</span><span class="sxs-lookup"><span data-stu-id="109c5-138">The candidate name is the same as the name of a tuple member, such as `Item3`, `Rest`, or `ToString`.</span></span>

- <span data-ttu-id="109c5-139">후보 이름이 튜플에 중복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-139">The candidate name is duplicated in the tuple.</span></span>

<span data-ttu-id="109c5-140">필드 이름 유추가 실패 하면 Visual Basic는 컴파일러 오류를 생성 하지 않으며 런타임에 예외가 throw 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-140">When field name inference fails, Visual Basic does not generate a compiler error, nor is an exception thrown at runtime.</span></span> <span data-ttu-id="109c5-141">대신, 튜플 필드는 및와 같은 미리 정의 된 이름으로 참조 되어야 합니다 `Item1` `Item2` .</span><span class="sxs-lookup"><span data-stu-id="109c5-141">Instead, tuple fields must be referenced by their predefined names, such as `Item1` and `Item2`.</span></span>

## <a name="tuples-versus-structures"></a><span data-ttu-id="109c5-142">튜플 및 구조체</span><span class="sxs-lookup"><span data-stu-id="109c5-142">Tuples versus structures</span></span>

<span data-ttu-id="109c5-143">Visual Basic 튜플은 **system.valuetuple** 제네릭 형식 중 하나의 인스턴스인 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-143">A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types.</span></span> <span data-ttu-id="109c5-144">예를 들어 `holiday` 이전 예제에서 정의 된 튜플은 구조체의 인스턴스입니다 <xref:System.ValueTuple%603> .</span><span class="sxs-lookup"><span data-stu-id="109c5-144">For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure.</span></span> <span data-ttu-id="109c5-145">데이터에 대 한 간단한 컨테이너로 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-145">It is designed to be a lightweight container for data.</span></span> <span data-ttu-id="109c5-146">튜플은 여러 데이터 항목을 사용 하 여 개체를 쉽게 만들 수 있도록 하기 때문에 사용자 지정 구조에 포함 될 수 있는 일부 기능이 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-146">Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have.</span></span> <span data-ttu-id="109c5-147">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-147">These include:</span></span>

- <span data-ttu-id="109c5-148">사용자 지정 멤버.</span><span class="sxs-lookup"><span data-stu-id="109c5-148">Custom members.</span></span> <span data-ttu-id="109c5-149">튜플에 대해 고유한 속성, 메서드 또는 이벤트를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-149">You cannot define your own properties, methods, or events for a tuple.</span></span>

- <span data-ttu-id="109c5-150">유효성 검사 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="109c5-150">Validation.</span></span> <span data-ttu-id="109c5-151">필드에 할당 된 데이터의 유효성을 검사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-151">You cannot validate the data assigned to fields.</span></span>

- <span data-ttu-id="109c5-152">불변성.</span><span class="sxs-lookup"><span data-stu-id="109c5-152">Immutability.</span></span> <span data-ttu-id="109c5-153">Visual Basic 튜플을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-153">Visual Basic tuples are mutable.</span></span> <span data-ttu-id="109c5-154">반면, 사용자 지정 구조를 사용 하면 인스턴스를 변경할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-154">In contrast, a custom structure allows you to control whether an instance is mutable or immutable.</span></span>

<span data-ttu-id="109c5-155">사용자 지정 멤버, 속성 및 필드 유효성 검사 또는 불변성이 중요 한 경우에는 Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) 문을 사용 하 여 사용자 지정 값 형식을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-155">If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.</span></span>

<span data-ttu-id="109c5-156">Visual Basic 튜플은 **system.valuetuple** 형식의 멤버를 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-156">A Visual Basic tuple does inherit the members of its **ValueTuple** type.</span></span> <span data-ttu-id="109c5-157">이러한 필드 외에도 다음과 같은 메서드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-157">In addition to its fields, these include the following methods:</span></span>

| <span data-ttu-id="109c5-158">방법</span><span class="sxs-lookup"><span data-stu-id="109c5-158">Method</span></span> | <span data-ttu-id="109c5-159">설명</span><span class="sxs-lookup"><span data-stu-id="109c5-159">Description</span></span> |
| ---|---|
| <span data-ttu-id="109c5-160">CompareTo</span><span class="sxs-lookup"><span data-stu-id="109c5-160">CompareTo</span></span> | <span data-ttu-id="109c5-161">현재 튜플을 동일한 수의 요소를 사용 하는 다른 튜플로 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-161">Compares the current tuple to another tuple with the same number of elements.</span></span> |
| <span data-ttu-id="109c5-162">같음</span><span class="sxs-lookup"><span data-stu-id="109c5-162">Equals</span></span> | <span data-ttu-id="109c5-163">현재 튜플이 다른 튜플 또는 개체와 같은지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-163">Determines whether the current tuple is equal to another tuple or object.</span></span> |
| <span data-ttu-id="109c5-164">GetHashCode</span><span class="sxs-lookup"><span data-stu-id="109c5-164">GetHashCode</span></span> | <span data-ttu-id="109c5-165">현재 인스턴스에 대 한 해시 코드를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-165">Calculates the hash code for the current instance.</span></span> |
| <span data-ttu-id="109c5-166">ToString</span><span class="sxs-lookup"><span data-stu-id="109c5-166">ToString</span></span> | <span data-ttu-id="109c5-167">형식을 사용 하는이 튜플의 문자열 표현을 반환 합니다 `(Item1, Item2...)` . 여기서 및는 `Item1` `Item2` 튜플의 필드 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-167">Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields.</span></span> |

<span data-ttu-id="109c5-168">또한 **system.valuetuple** 형식은 <xref:System.Collections.IStructuralComparable> <xref:System.Collections.IStructuralEquatable> 사용자 지정 비교자를 정의 하는 데 사용할 수 있는 및 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-168">In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define custom comparers.</span></span>

## <a name="assignment-and-tuples"></a><span data-ttu-id="109c5-169">할당 및 튜플</span><span class="sxs-lookup"><span data-stu-id="109c5-169">Assignment and tuples</span></span>

<span data-ttu-id="109c5-170">Visual Basic는 필드 수가 같은 튜플 형식 간의 할당을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-170">Visual Basic supports assignment between tuple types that have the same number of fields.</span></span> <span data-ttu-id="109c5-171">다음 조건 중 하나에 해당 하는 경우 필드 형식을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-171">The field types can be converted if one of the following is true:</span></span>

- <span data-ttu-id="109c5-172">원본 및 대상 필드의 형식이 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-172">The source and target field are of the same type.</span></span>

- <span data-ttu-id="109c5-173">원본 형식에서 대상 형식으로의 확대 또는 암시적 변환이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-173">A widening (or implicit) conversion of the source type to the target type is defined.</span></span>

- <span data-ttu-id="109c5-174">`Option Strict` 가이 `On` 고 원본 형식에서 대상 형식으로의 축소 또는 명시적 변환이 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-174">`Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined.</span></span> <span data-ttu-id="109c5-175">소스 값이 대상 형식의 범위를 벗어나면이 변환에서 예외를 throw 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-175">This conversion can throw an exception if the source value is outside the range of the target type.</span></span>

<span data-ttu-id="109c5-176">다른 변환은 할당에 고려되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-176">Other conversions are not considered for assignments.</span></span> <span data-ttu-id="109c5-177">튜플 형식 간에 허용되는 할당 종류를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-177">Let's look at the kinds of assignments that are allowed between tuple types.</span></span>

<span data-ttu-id="109c5-178">다음 예제에서 사용되는 이러한 변수를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="109c5-178">Consider these variables used in the following examples:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

<span data-ttu-id="109c5-179">처음 두 변수인 및에 `unnamed` 는 `anonymous` 필드에 대해 지정 된 의미 체계 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-179">The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields.</span></span> <span data-ttu-id="109c5-180">필드 이름은 기본 `Item1` 및 `Item2` 입니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-180">Their field names are the default `Item1` and `Item2`.</span></span> <span data-ttu-id="109c5-181">마지막 두 변수인 및에 `named` 는 `differentName` 의미 체계 필드 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-181">The last two variables, `named` and `differentName` have semantic field names.</span></span> <span data-ttu-id="109c5-182">이러한 두 튜플의 필드 이름은 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-182">Note that these two tuples have different names for the fields.</span></span>

<span data-ttu-id="109c5-183">이러한 튜플 중 4 개는 동일한 수의 필드 (' 인자 ' 라고 함)를 포함 하 고 이러한 필드의 형식은 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-183">All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical.</span></span> <span data-ttu-id="109c5-184">따라서 다음 할당이 모든 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-184">Therefore, all of these assignments work:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

<span data-ttu-id="109c5-185">튜플 이름은 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-185">Notice that the names of the tuples are not assigned.</span></span> <span data-ttu-id="109c5-186">필드 값은 튜플의 필드 순서에 따라 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-186">The values of the fields are assigned following the order of the fields in the tuple.</span></span>

<span data-ttu-id="109c5-187">마지막으로 `named` `conversion` 의 첫 번째 필드가 `named` 이 `Integer` 고의 첫 번째 `conversion` `Long` 필드가 인 경우에도 튜플에 튜플을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-187">Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`.</span></span> <span data-ttu-id="109c5-188">`Integer`을로 변환 하는 `Long` 것은 확대 변환 이므로이 할당은 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-188">This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

<span data-ttu-id="109c5-189">필드 수가 다른 튜플은 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-189">Tuples with different numbers of fields are not assignable:</span></span>

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a><span data-ttu-id="109c5-190">메서드 반환 값으로의 튜플</span><span class="sxs-lookup"><span data-stu-id="109c5-190">Tuples as method return values</span></span>

<span data-ttu-id="109c5-191">메서드는 단일 값만 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-191">A method can return only a single value.</span></span> <span data-ttu-id="109c5-192">그러나 메서드를 호출 하 여 여러 값을 반환 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-192">Frequently, though, you'd like a method call to return multiple values.</span></span> <span data-ttu-id="109c5-193">이 제한 사항을 해결 하는 데는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-193">There are several ways to work around this limitation:</span></span>

- <span data-ttu-id="109c5-194">속성이 나 필드가 메서드에서 반환 된 값을 나타내는 사용자 지정 클래스 또는 구조체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-194">You can create a custom class or structure whose properties or fields represent values returned by the method.</span></span> <span data-ttu-id="109c5-195">따라서는 고중량 솔루션입니다. 메서드 호출에서 값을 검색 하는 용도로만 사용 되는 사용자 지정 형식을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-195">Thus is a heavyweight solution; it requires that you define a custom type whose only purpose is to retrieve values from a method call.</span></span>

- <span data-ttu-id="109c5-196">메서드에서 단일 값을 반환 하 고, 메서드에 대 한 참조로 전달 하 여 나머지 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-196">You can return a single value from the method, and return the remaining values by passing them by reference to the method.</span></span> <span data-ttu-id="109c5-197">여기에는 변수를 인스턴스화하는 오버 헤드가 발생 하며 실수로 참조로 전달 하는 변수의 값을 덮어쓰는 위험이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-197">This involves the overhead of instantiating a variable and risks inadvertently overwriting the value of the variable that you pass by reference.</span></span>

- <span data-ttu-id="109c5-198">여러 반환 값을 검색 하는 간단한 솔루션을 제공 하는 튜플을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-198">You can use a tuple, which provides a lightweight solution to retrieving multiple return values.</span></span>

<span data-ttu-id="109c5-199">예를 들어 .NET의 **TryParse** 메서드는 `Boolean` 구문 분석 작업이 성공 했는지 여부를 나타내는 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-199">For example, the **TryParse** methods in .NET return a `Boolean` value that indicates whether the parsing operation succeeded.</span></span> <span data-ttu-id="109c5-200">구문 분석 작업의 결과는 메서드에 대 한 참조로 전달 된 변수에 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-200">The result of the parsing operation is returned in a variable passed by reference to the method.</span></span> <span data-ttu-id="109c5-201">일반적으로와 같은 구문 분석 메서드를 호출 하는 것은 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-201">Normally, a call to the a parsing method such as <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> looks like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

<span data-ttu-id="109c5-202">자체 메서드에서 메서드에 대 한 호출을 래핑하는 경우 구문 분석 작업에서 튜플을 반환할 수 있습니다 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="109c5-202">We can return a tuple from the parsing operation if we wrap the call to the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method in our own method.</span></span> <span data-ttu-id="109c5-203">다음 예제에서는 메서드를 `NumericLibrary.ParseInteger` 호출 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 하 고 두 개의 요소가 있는 명명 된 튜플을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-203">In the following example, `NumericLibrary.ParseInteger` calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method and returns a named tuple with two elements.</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

<span data-ttu-id="109c5-204">그런 다음 다음과 같은 코드를 사용 하 여 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-204">You can then call the method with code like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a><span data-ttu-id="109c5-205">.NET Framework에서 튜플 및 튜플 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="109c5-205">Visual Basic tuples and tuples in the .NET Framework</span></span>

<span data-ttu-id="109c5-206">Visual Basic 튜플은 .NET Framework 4.7에 도입 된 **system.valuetuple** 제네릭 형식 중 하나의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-206">A Visual Basic tuple is an instance of one of the **System.ValueTuple** generic types, which were introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="109c5-207">또한 .NET Framework에 **는 제네릭 system.string** 클래스 집합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-207">The .NET Framework also includes a set of generic **System.Tuple** classes.</span></span> <span data-ttu-id="109c5-208">그러나 이러한 클래스는 Visual Basic 튜플 및 여러 가지 방법으로 **system.valuetuple** 제네릭 형식과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-208">These classes, however, differ from Visual Basic tuples and the **System.ValueTuple** generic types in a number of ways:</span></span>

- <span data-ttu-id="109c5-209">**튜플** 클래스의 요소는, 등의 속성 `Item1` `Item2` 입니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-209">The elements of the **Tuple** classes are properties named `Item1`, `Item2`, and so on.</span></span> <span data-ttu-id="109c5-210">Visual Basic 튜플 및 **system.valuetuple** 형식에서 튜플 요소는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-210">In Visual Basic tuples and the **ValueTuple** types, tuple elements are fields.</span></span>

- <span data-ttu-id="109c5-211">**튜플** 인스턴스 또는 **system.valuetuple** 인스턴스의 요소에 의미 있는 이름을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-211">You cannot assign meaningful names to the elements of a **Tuple** instance or of a **ValueTuple** instance.</span></span> <span data-ttu-id="109c5-212">Visual Basic를 사용 하 여 필드의 의미를 전달 하는 이름을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-212">Visual Basic allows you to assign names that communicate the meaning of the fields.</span></span>

- <span data-ttu-id="109c5-213">**튜플** 인스턴스의 속성은 읽기 전용입니다. 튜플을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-213">The properties of a **Tuple** instance are read-only; the tuples are immutable.</span></span> <span data-ttu-id="109c5-214">Visual Basic 튜플 및 **system.valuetuple** 형식에서 튜플 필드는 읽기/쓰기입니다. 튜플을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-214">In Visual Basic tuples and the **ValueTuple** types, tuple fields are read-write; the tuples are mutable.</span></span>

- <span data-ttu-id="109c5-215">제네릭 **튜플** 형식은 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-215">The generic **Tuple** types are reference types.</span></span> <span data-ttu-id="109c5-216">이러한 **튜플** 형식을 사용 하면 개체 할당을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-216">Using these **Tuple** types means allocating objects.</span></span> <span data-ttu-id="109c5-217">실행 부하 과다 경로에서는 이로 인해 애플리케이션 성능이 크게 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-217">On hot paths, this can have a measurable impact on your application's performance.</span></span> <span data-ttu-id="109c5-218">Visual Basic 튜플 및 **system.valuetuple** 형식은 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-218">Visual Basic tuples and the **ValueTuple** types are value types.</span></span>

<span data-ttu-id="109c5-219">클래스의 확장 메서드를 사용 <xref:System.TupleExtensions> 하면 Visual Basic 튜플 및 .Net **튜플** 개체 간에 쉽게 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-219">Extension methods in the <xref:System.TupleExtensions> class make it easy to convert between Visual Basic tuples and .NET **Tuple** objects.</span></span> <span data-ttu-id="109c5-220">**Totuple** 메서드는 Visual Basic 튜플을 .net **튜플** 개체로 변환 하 고, **ToValueTuple** 메서드는 .net **튜플** 개체를 Visual Basic 튜플로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-220">The **ToTuple** method converts a Visual Basic tuple to a .NET **Tuple** object, and the **ToValueTuple** method converts a .NET **Tuple** object to a Visual Basic tuple.</span></span>

<span data-ttu-id="109c5-221">다음 예제에서는 튜플을 만들고 .NET **튜플** 개체로 변환한 다음 다시 Visual Basic 튜플로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-221">The following example creates a tuple, converts it to a .NET **Tuple** object, and converts it back to a Visual Basic tuple.</span></span> <span data-ttu-id="109c5-222">그런 다음이 튜플을 원래 튜플과 비교 하 여 동일한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="109c5-222">The example then compares this tuple with the original one to ensure that they are equal.</span></span>

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a><span data-ttu-id="109c5-223">참조</span><span class="sxs-lookup"><span data-stu-id="109c5-223">See also</span></span>

- [<span data-ttu-id="109c5-224">Visual Basic 언어 참조</span><span class="sxs-lookup"><span data-stu-id="109c5-224">Visual Basic Language Reference</span></span>](index.md)
