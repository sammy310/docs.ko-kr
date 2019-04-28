---
title: Visual Basic의 튜플
ms.date: 04/23/2017
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
ms.openlocfilehash: 146e9c2360cea153d2f487769d5b983516861e8d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663299"
---
# <a name="tuples-visual-basic"></a><span data-ttu-id="b8e9a-102">튜플 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8e9a-102">Tuples (Visual Basic)</span></span>

<span data-ttu-id="b8e9a-103">Visual Basic 2017부터 Visual Basic 언어를 제공 하는 튜플에 대 한 기본 제공 지원을 튜플 만들기 및 쉽게 튜플의 요소에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-103">Starting with Visual Basic 2017, the Visual Basic language offers built-in support for tuples that makes creating tuples and accessing the elements of tuples easier.</span></span> <span data-ttu-id="b8e9a-104">튜플은 값의 시퀀스를 특정 수 있는 간단한 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-104">A tuple is a light-weight data structure that has a specific number and sequence of values.</span></span> <span data-ttu-id="b8e9a-105">튜플을 인스턴스화할 수 및 각 값 (또는 요소)의 데이터 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-105">When you instantiate the tuple, you define the number and the data type of each value (or element).</span></span> <span data-ttu-id="b8e9a-106">예를 들어 2 개 튜플 (또는 쌍)에 두 개의 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-106">For example, a 2-tuple (or pair) has two elements.</span></span> <span data-ttu-id="b8e9a-107">첫 번째 수를 `Boolean` 값을 두 번째는는 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-107">The first might be a `Boolean` value, while the second is a `String`.</span></span> <span data-ttu-id="b8e9a-108">튜플을 사용 하면 쉽게 단일 개체에 여러 값을 저장, 때문에 종종 메서드에서 여러 값을 반환 하는 간단한 방법으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-108">Because tuples make it easy to store multiple values in a single object, they are often used as a lightweight way to return multiple values from a method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8e9a-109">튜플 지원에 필요 합니다 <xref:System.ValueTuple> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-109">Tuple support requires the <xref:System.ValueTuple> type.</span></span> <span data-ttu-id="b8e9a-110">.NET Framework 4.7을 설치 하지 않은 경우에 NuGet 패키지를 추가 해야 `System.ValueTuple`은 NuGet 갤러리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-110">If the .NET Framework 4.7 is not installed, you must add the NuGet package `System.ValueTuple`, which is available on the NuGet Gallery.</span></span> <span data-ttu-id="b8e9a-111">이 패키지가 없으면 오류가 발생할 수 있습니다를 컴파일, "미리 정의 된 형식과 비슷한 'ValueTuple(Of,,,)'가 정의 하지 않았거나 가져오지 하지 않습니다."</span><span class="sxs-lookup"><span data-stu-id="b8e9a-111">Without this package, you may get a compilation error similar to, "Predefined type 'ValueTuple(Of,,,)' is not defined or imported."</span></span>

## <a name="instantiating-and-using-a-tuple"></a><span data-ttu-id="b8e9a-112">인스턴스화하고 튜플을 사용</span><span class="sxs-lookup"><span data-stu-id="b8e9a-112">Instantiating and using a tuple</span></span>

<span data-ttu-id="b8e9a-113">쉼표로 구분 된 값 im 괄호에 묶어 튜플을 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-113">You instantiate a tuple by enclosing its comma-delimited values im parentheses.</span></span> <span data-ttu-id="b8e9a-114">각 값 튜플의 필드가 다음 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-114">Each of those values then becomes a field of the tuple.</span></span> <span data-ttu-id="b8e9a-115">다음 코드를 사용 하 여 세 번 (또는 3 튜플)을 정의 예를 들어를 `Date` 첫 번째 값으로는 `String` 를 해당 두 번째 및 `Boolean` 세 번째도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-115">For example, the following code defines a triple (or 3-tuple) with a `Date` as its first value, a `String` as its second, and a `Boolean` as its third.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

<span data-ttu-id="b8e9a-116">튜플의 각 필드의 이름은 기본적으로 문자열의 구성 `Item` 튜플의 필드의 1부터 시작 위치와 함께 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-116">By default, the name of each field in a tuple consists of the string `Item` along with the field's one-based position in the tuple.</span></span> <span data-ttu-id="b8e9a-117">이 3 개 튜플에 대 한 합니다 `Date` 필드는 `Item1`, `String` 필드가 `Item2`, 및 `Boolean` 필드는 `Item3`합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-117">For this 3-tuple, the `Date` field is `Item1`, the `String` field is `Item2`, and the `Boolean` field is `Item3`.</span></span> <span data-ttu-id="b8e9a-118">다음 예제에서는 이전 코드 줄에서 인스턴스화됩니다 튜플 필드의 값을 표시</span><span class="sxs-lookup"><span data-stu-id="b8e9a-118">The following example displays the values of fields of the tuple instantiated in the previous line of code</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

<span data-ttu-id="b8e9a-119">Visual Basic 튜플의 필드는 읽기-쓰기입니다. 튜플을 인스턴스화한 후에 해당 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-119">The fields of a Visual Basic tuple are read-write; after you've instantiated a tuple, you can modify its values.</span></span> <span data-ttu-id="b8e9a-120">다음 예제에서는 두 개의 이전 예에서 만든 튜플의 세 필드를 수정 하 고 결과 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-120">The following example modifies two of the three fields of the tuple created in the previous example and displays the result.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a><span data-ttu-id="b8e9a-121">인스턴스화 및 명명 된 튜플을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="b8e9a-121">Instantiating and using a named tuple</span></span>

<span data-ttu-id="b8e9a-122">인스턴스화할 수는 튜플 필드에 대 한 기본 이름을 사용 하는 대신 한 *명명 된 튜플* 튜플의 요소에 고유한 이름을 할당 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-122">Rather than using default names for a tuple's fields, you can instantiate a *named tuple* by assigning your own names to the tuple's elements.</span></span> <span data-ttu-id="b8e9a-123">튜플의 필드에 할당 된 이름으로 액세스할 수 있습니다 *또는* 기본 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-123">The tuple's fields can then be accessed by their assigned names *or* by their default names.</span></span> <span data-ttu-id="b8e9a-124">다음 예제에서는 첫 번째 필드 이름을 명시적으로 제외 하 고 앞에서 동일한 3 튜플을 인스턴스화합니다 `EventDate`, 두 번째 `Name`, 및 세 번째 `IsHoliday`입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-124">The following example instantiates the same 3-tuple as previously, except that it explicitly names the first field `EventDate`, the second `Name`, and the third `IsHoliday`.</span></span> <span data-ttu-id="b8e9a-125">다음 필드 값을 표시, 수정 하 고 필드 값을 다시 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-125">It then displays the field values, modifies them, and displays the field values again.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="b8e9a-126">유추된 튜플 요소 이름</span><span class="sxs-lookup"><span data-stu-id="b8e9a-126">Inferred tuple element names</span></span>

<span data-ttu-id="b8e9a-127">Visual Basic 15.3부터 Visual Basic 유추할 수 있는 튜플 요소 이름 명시적으로 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-127">Starting with Visual Basic 15.3, Visual Basic can infer the names of tuple elements; you do not have to assign them explicitly.</span></span> <span data-ttu-id="b8e9a-128">유추 된 튜플 이름 변수의 집합에서 튜플을 초기화할 튜플 요소 이름은 변수 이름과 동일 하도록 하려는 경우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-128">Inferred tuple names are useful when you initialize a tuple from a set of variables, and you want the tuple element name to be the same as the variable name.</span></span> 

<span data-ttu-id="b8e9a-129">다음 예에서는 `stateInfo` 명명 된 요소, 3을 명시적으로 포함 된 튜플을 `state`를 `stateName`, 및 `capital`합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-129">The following example creates a `stateInfo` tuple that contains three explicitly named elements, `state`, `stateName`, and `capital`.</span></span> <span data-ttu-id="b8e9a-130">명명 된 요소에서, 튜플 초기화 문의 할당 명명 된 요소를 동일 하 게 명명 된 변수의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-130">Note that, in naming the elements, the tuple initialization statement simply assigns the named elements the values of the identically named variables.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
<span data-ttu-id="b8e9a-131">요소 및 변수 이름이 있으므로 Visual Basic 컴파일러는 다음 예제와 같이 필드의 이름을 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-131">Because elements and variables have the same name, the Visual Basic compiler can infer the names of the fields, as the following example shows.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

<span data-ttu-id="b8e9a-132">유추 된 튜플 요소 이름을 사용 하도록 설정, Visual Basic 프로젝트에서는 Visual Basic 컴파일러의 버전을 정의 해야 합니다 (\*.vbproj) 파일:</span><span class="sxs-lookup"><span data-stu-id="b8e9a-132">To enable inferred tuple element names, you must define the version of the Visual Basic compiler to use in your Visual Basic project (\*.vbproj) file:</span></span> 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 
```

<span data-ttu-id="b8e9a-133">버전 번호는 15.3부터 Visual Basic 컴파일러의 버전일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-133">The version number can be any version of the Visual Basic compiler starting with 15.3.</span></span> <span data-ttu-id="b8e9a-134">하드 코딩 특정 컴파일러 버전을 대신 지정할 수도 있습니다 "Latest" 값으로 `LangVersion` 시스템에 설치 하는 Visual Basic 컴파일러의 최신 버전을 사용 하 여 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-134">Rather than hard-coding a specific compiler version, you can also specify "Latest" as the value of `LangVersion` to compile with the most recent version of the Visual Basic compiler installed on your system.</span></span>

<span data-ttu-id="b8e9a-135">자세한 내용은 [Visual Basic 언어 버전을 설정](../../../language-reference/configure-language-version.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-135">For more information, see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

<span data-ttu-id="b8e9a-136">경우에 따라 Visual Basic 컴파일러에는 후보 이름에서 튜플 요소 이름을 유추할 수 없습니다 및와 같은 기본 이름으로 사용 하 여 튜플 필드 참조만 수 `Item1`, `Item2`등입니다. 여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-136">In some cases, the Visual Basic compiler cannot infer the tuple element name from the candidate name, and the tuple field can only be referenced using its default name, such as `Item1`, `Item2`, etc. These include:</span></span>

- <span data-ttu-id="b8e9a-137">후보 이름이 튜플 멤버의 이름과 같은 `Item3`, `Rest`, 또는 `ToString`합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-137">The candidate name is the same as the name of a tuple member, such as `Item3`, `Rest`, or `ToString`.</span></span>

- <span data-ttu-id="b8e9a-138">튜플의 후보 이름이 중복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-138">The candidate name is duplicated in the tuple.</span></span>
 
<span data-ttu-id="b8e9a-139">필드 이름 유추가 실패 하면 Visual Basic 컴파일러 오류를 생성 하지 않습니다 없거나 런타임에 발생 하는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-139">When field name inference fails, Visual Basic does not generate a compiler error, nor is an exception thrown at runtime.</span></span> <span data-ttu-id="b8e9a-140">대신 튜플 필드 참조 해야 합니다는 미리 정의 된 이름으로 같은 `Item1` 고 `Item2`입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-140">Instead, tuple fields must be referenced by their predefined names, such as `Item1` and `Item2`.</span></span> 
  
## <a name="tuples-versus-structures"></a><span data-ttu-id="b8e9a-141">구조체 및 튜플</span><span class="sxs-lookup"><span data-stu-id="b8e9a-141">Tuples versus structures</span></span>

<span data-ttu-id="b8e9a-142">Visual Basic 튜플 값 형식인 중 하나의 인스턴스는 합니다는 **System.ValueTuple** 제네릭 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-142">A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types.</span></span> <span data-ttu-id="b8e9a-143">예를 들어 합니다 `holiday` 의 인스턴스가 이전 예제에서 정의 된 튜플을 <xref:System.ValueTuple%603> 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-143">For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure.</span></span> <span data-ttu-id="b8e9a-144">데이터에 대 한 간단한 컨테이너 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-144">It is designed to be a lightweight container for data.</span></span> <span data-ttu-id="b8e9a-145">튜플에 여러 데이터 항목을 사용 하 여 개체를 만들 수 있도록 하려고, 있으므로 사용자 정의 구조를 가질 수 있는 기능 중 일부는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-145">Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have.</span></span> <span data-ttu-id="b8e9a-146">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-146">These include:</span></span>

- <span data-ttu-id="b8e9a-147">사용자 지정 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-147">Custom members.</span></span> <span data-ttu-id="b8e9a-148">사용자 고유의 속성, 메서드 또는 튜플에 대 한 이벤트를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-148">You cannot define your own properties, methods, or events for a tuple.</span></span>

- <span data-ttu-id="b8e9a-149">유효성 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-149">Validation.</span></span> <span data-ttu-id="b8e9a-150">필드에 할당 된 데이터를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-150">You cannot validate the data assigned to fields.</span></span>

- <span data-ttu-id="b8e9a-151">불변성입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-151">Immutability.</span></span> <span data-ttu-id="b8e9a-152">Visual Basic 튜플은 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-152">Visual Basic tuples are mutable.</span></span> <span data-ttu-id="b8e9a-153">반면, 사용자 정의 구조를 제어할 수 있습니다 인스턴스는 변경할 수 없는 또는 변경할 수 있는지 여부를 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-153">In contrast, a custom structure allows you to control whether an instance is mutable or immutable.</span></span>

<span data-ttu-id="b8e9a-154">사용자 지정 멤버, 속성 및 필드 유효성 검사 또는 불변성이 중요 한 경우에 Visual Basic을 사용 해야 [구조](../../../language-reference/statements/structure-statement.md) 문을 사용자 지정 값 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-154">If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.</span></span>

<span data-ttu-id="b8e9a-155">Visual Basic 튜플을의 멤버를 상속 하는 해당 **ValueTuple** 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-155">A Visual Basic tuple does inherit the members of its **ValueTuple** type.</span></span> <span data-ttu-id="b8e9a-156">해당 필드 외에 다음 메서드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-156">In addition to its fields, these include the following methods:</span></span>

| <span data-ttu-id="b8e9a-157">멤버</span><span class="sxs-lookup"><span data-stu-id="b8e9a-157">Member</span></span> | <span data-ttu-id="b8e9a-158">설명</span><span class="sxs-lookup"><span data-stu-id="b8e9a-158">Description</span></span> |
| ---|---|
| <span data-ttu-id="b8e9a-159">CompareTo</span><span class="sxs-lookup"><span data-stu-id="b8e9a-159">CompareTo</span></span> | <span data-ttu-id="b8e9a-160">동일한 요소 수를 사용 하 여 다른 튜플을 현재 튜플을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-160">Compares the current tuple to another tuple with the same number of elements.</span></span> |
| <span data-ttu-id="b8e9a-161">같음</span><span class="sxs-lookup"><span data-stu-id="b8e9a-161">Equals</span></span> | <span data-ttu-id="b8e9a-162">현재 튜플을 다른 튜플 또는 개체와 같은지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-162">Determines whether the current tuple is equal to another tuple or object.</span></span> |
| <span data-ttu-id="b8e9a-163">GetHashCode</span><span class="sxs-lookup"><span data-stu-id="b8e9a-163">GetHashCode</span></span> | <span data-ttu-id="b8e9a-164">현재 인스턴스의 해시 코드를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-164">Calculates the hash code for the current instance.</span></span> |
| <span data-ttu-id="b8e9a-165">ToString</span><span class="sxs-lookup"><span data-stu-id="b8e9a-165">ToString</span></span> | <span data-ttu-id="b8e9a-166">폼을 사용 하는이 튜플의 문자열 표현을 반환 `(Item1, Item2...)`, 여기서 `Item1` 및 `Item2` 튜플의 필드의 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-166">Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields.</span></span> |

<span data-ttu-id="b8e9a-167">또한 합니다 **ValueTuple** 형식은 구현 <xref:System.Collections.IStructuralComparable> 및 <xref:System.Collections.IStructuralEquatable> 인터페이스 고객 비교자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-167">In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.</span></span>

## <a name="assignment-and-tuples"></a><span data-ttu-id="b8e9a-168">할당 및 튜플</span><span class="sxs-lookup"><span data-stu-id="b8e9a-168">Assignment and tuples</span></span>

<span data-ttu-id="b8e9a-169">Visual Basic는 필드 수가 같은 튜플 형식 간의 할당을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-169">Visual Basic supports assignment between tuple types that have the same number of fields.</span></span> <span data-ttu-id="b8e9a-170">다음 중 하나가 참인 경우에 필드 유형은 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-170">The field types can be converted if one of the following is true:</span></span>

- <span data-ttu-id="b8e9a-171">원본 및 대상 필드는 동일한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-171">The source and target field are of the same type.</span></span>

- <span data-ttu-id="b8e9a-172">확대 (또는 암시적) 변환 원본 유형 대상 유형으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-172">A widening (or implicit) conversion of the source type to the target type is defined.</span></span> 

- <span data-ttu-id="b8e9a-173">`Option Strict` `On`, 축소 (또는 명시적) 변환 원본 유형 대상 유형으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-173">`Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined.</span></span> <span data-ttu-id="b8e9a-174">이 변환 원본 값이 대상 형식의 범위를 벗어난 경우 예외가 throw 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-174">This conversion can throw an exception if the source value is outside the range of the target type.</span></span>

<span data-ttu-id="b8e9a-175">다른 변환은 할당에 고려되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-175">Other conversions are not considered for assignments.</span></span> <span data-ttu-id="b8e9a-176">튜플 형식 간에 허용되는 할당 종류를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-176">Let's look at the kinds of assignments that are allowed between tuple types.</span></span>

<span data-ttu-id="b8e9a-177">다음 예제에서 사용되는 이러한 변수를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-177">Consider these variables used in the following examples:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

<span data-ttu-id="b8e9a-178">처음 두 변수인 `unnamed` 고 `anonymous`, 필드에 대해 제공 된 의미 체계 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-178">The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields.</span></span> <span data-ttu-id="b8e9a-179">해당 필드 이름은 기본값 `Item1` 고 `Item2`입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-179">Their field names are the default `Item1` and `Item2`.</span></span> <span data-ttu-id="b8e9a-180">마지막 두 변수인 `named` 고 `differentName` 의미 체계 필드 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-180">The last two variables, `named` and `differentName` have semantic field names.</span></span> <span data-ttu-id="b8e9a-181">이러한 두 튜플의 필드 이름은 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-181">Note that these two tuples have different names for the fields.</span></span>

<span data-ttu-id="b8e9a-182">모든 이러한 네 튜플에서 필드 (라고 '인자 수')에 동일한 수 있고 해당 필드의 형식이 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-182">All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical.</span></span> <span data-ttu-id="b8e9a-183">따라서 다음 할당이 모든 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-183">Therefore, all of these assignments work:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

<span data-ttu-id="b8e9a-184">튜플 이름은 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-184">Notice that the names of the tuples are not assigned.</span></span> <span data-ttu-id="b8e9a-185">필드 값은 튜플의 필드 순서에 따라 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-185">The values of the fields are assigned following the order of the fields in the tuple.</span></span>

<span data-ttu-id="b8e9a-186">마지막으로 할당할 수 있습니다는 알 수 있습니다는 `named` tuple를 `conversion` 튜플도의 첫 번째 필드 `named` 는 `Integer`, 및의 첫 번째 필드 `conversion` 는 `Long`.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-186">Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`.</span></span> <span data-ttu-id="b8e9a-187">변환 때문에이 할당 성공를 `Integer` 에 `Long` 확대 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-187">This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

<span data-ttu-id="b8e9a-188">필드 수가 각기 다른 튜플은 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-188">Tuples with different numbers of fields are not assignable:</span></span>

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a><span data-ttu-id="b8e9a-189">메서드 반환 값으로의 튜플</span><span class="sxs-lookup"><span data-stu-id="b8e9a-189">Tuples as method return values</span></span>

<span data-ttu-id="b8e9a-190">메서드는 단일 값만 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-190">A method can return only a single value.</span></span> <span data-ttu-id="b8e9a-191">자주 하지만 원하는 메서드 호출을 여러 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-191">Frequently, though, you'd like a method call to return multiple values.</span></span> <span data-ttu-id="b8e9a-192">이 제한을 해결 하는 방법은 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-192">There are several ways to work around this limitation:</span></span>

- <span data-ttu-id="b8e9a-193">사용자 지정 클래스 또는 구조체 속성이 만들거나 필드 메서드에 의해 반환 되는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-193">You can create a custom class or structure whose properties or fields represent values returned by the method.</span></span> <span data-ttu-id="b8e9a-194">따라서는 대규모 솔루션입니다. 메서드 호출에서 값을 검색할 위해서만 사용 되는 사용자 지정 형식을 정의 하는 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-194">Thus is a heavyweight solution; it requires that you define a custom type whose only purpose is to retrieve values from a method call.</span></span>

- <span data-ttu-id="b8e9a-195">메서드에서 단일 값을 반환 하 고 메서드에 참조로 전달 하 여 나머지 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-195">You can return a single value from the method, and return the remaining values by passing them by reference to the method.</span></span> <span data-ttu-id="b8e9a-196">여기에 변수 및 참조로 전달 하는 변수의 값을 덮어쓰는 위험을 인스턴스화하는 오버 헤드 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-196">This involves the overhead of instantiating a variable and risks inadvertently overwriting the value of the variable that you pass by reference.</span></span>

- <span data-ttu-id="b8e9a-197">여러 개의 반환 값을 검색 하는 간단한 솔루션을 제공 하는 튜플을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-197">You can use a tuple, which provides a lightweight solution to retrieving multiple return values.</span></span>

<span data-ttu-id="b8e9a-198">예를 들어 합니다 **TryParse** .NET 반환에서 메서드를 `Boolean` 구문 분석 작업이 성공 했는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-198">For example, the **TryParse** methods in .NET return a `Boolean` value that indicates whether the parsing operation succeeded.</span></span> <span data-ttu-id="b8e9a-199">구문 분석 작업의 결과 메서드가 참조로 전달 된 변수에 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-199">The result of the parsing operation is returned in a variable passed by reference to the method.</span></span> <span data-ttu-id="b8e9a-200">일반적으로 호출 하는 구문 분석 메서드와 같은 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 다음과 같습니다:</span><span class="sxs-lookup"><span data-stu-id="b8e9a-200">Normally, a call to the a parsing method such as <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> looks like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

<span data-ttu-id="b8e9a-201">호출을 래핑할 경우 구문 분석 작업에서 튜플을 반환할 수 있습니다는 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 고유한 메서드에서 메서드.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-201">We can return a tuple from the parsing operation if we wrap the call to the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method in our own method.</span></span> <span data-ttu-id="b8e9a-202">다음 예에서 `NumericLibrary.ParseInteger` 호출을 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 메서드 두 요소를 사용 하 여 명명 된 튜플을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-202">In the following example, `NumericLibrary.ParseInteger` calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method and returns a named tuple with two elements.</span></span> 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

<span data-ttu-id="b8e9a-203">다음과 같은 코드를 사용 하 여 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-203">You can then call the method with code like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a><span data-ttu-id="b8e9a-204">Visual Basic 튜플 및.NET Framework의 튜플</span><span class="sxs-lookup"><span data-stu-id="b8e9a-204">Visual Basic tuples and tuples in the .NET Framework</span></span>

<span data-ttu-id="b8e9a-205">Visual Basic 튜플은의 인스턴스를 **System.ValueTuple** .NET Framework 4.7에 도입 된 제네릭 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-205">A Visual Basic tuple is an instance of one of the **System.ValueTuple** generic types, which were introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="b8e9a-206">.NET Framework는 제네릭 집합에도 포함 되어 있습니다 **System.Tuple** 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-206">The .NET Framework also includes a set of generic **System.Tuple** classes.</span></span> <span data-ttu-id="b8e9a-207">그러나 Visual Basic 튜플에서 다를 이러한 클래스와 **System.ValueTuple** 의 다양 한 방법으로 제네릭 형식:</span><span class="sxs-lookup"><span data-stu-id="b8e9a-207">These classes, however, differ from Visual Basic tuples and the **System.ValueTuple** generic types in a number of ways:</span></span>

- <span data-ttu-id="b8e9a-208">요소를 **튜플** 클래스는 명명 된 속성 `Item1`, `Item2`등입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-208">The elements of the **Tuple** classes are properties named `Item1`, `Item2`, and so on.</span></span> <span data-ttu-id="b8e9a-209">Visual Basic 튜플에 포함에서 하며 **ValueTuple** 튜플 요소의 형식은 필드.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-209">In Visual Basic tuples and the **ValueTuple** types, tuple elements are fields.</span></span>

- <span data-ttu-id="b8e9a-210">요소에 의미 있는 이름을 할당할 수 없습니다는 **튜플** 인스턴스 또는의 **ValueTuple** 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-210">You cannot assign meaningful names to the elements of a **Tuple** instance or of a **ValueTuple** instance.</span></span> <span data-ttu-id="b8e9a-211">Visual Basic을 사용 하면 필드의 의미를 통신 하는 이름에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-211">Visual Basic allows you to assign names that communicate the meaning of the fields.</span></span>

- <span data-ttu-id="b8e9a-212">속성을 **튜플** 인스턴스는 읽기 전용; 튜플은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-212">The properties of a **Tuple** instance are read-only; the tuples are immutable.</span></span> <span data-ttu-id="b8e9a-213">Visual Basic 튜플 및 **ValueTuple** 형식, 튜플 필드는 읽기-쓰기; 튜플은 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-213">In Visual Basic tuples and the **ValueTuple** types, tuple fields are read-write; the tuples are mutable.</span></span>

- <span data-ttu-id="b8e9a-214">제네릭 **튜플** 형식은 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-214">The generic **Tuple** types are reference types.</span></span> <span data-ttu-id="b8e9a-215">이 사용 하 여 **튜플** 형식 개체를 할당 하는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-215">Using these **Tuple** types means allocating objects.</span></span> <span data-ttu-id="b8e9a-216">실행 부하 과다 경로에서는 이로 인해 애플리케이션 성능이 크게 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-216">On hot paths, this can have a measurable impact on your application's performance.</span></span> <span data-ttu-id="b8e9a-217">Visual Basic 튜플 및 **ValueTuple** 형식은 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-217">Visual Basic tuples and the **ValueTuple** types are value types.</span></span>

<span data-ttu-id="b8e9a-218">확장 메서드는 <xref:System.TupleExtensions> 클래스를 쉽게 Visual Basic 튜플와.NET 간 변환 **튜플** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-218">Extension methods in the <xref:System.TupleExtensions> class make it easy to convert between Visual Basic tuples and .NET **Tuple** objects.</span></span> <span data-ttu-id="b8e9a-219">**ToTuple** 메서드는.NET Visual Basic 튜플을 변환 합니다 **튜플** 개체와 **ToValueTuple** 메서드를.NET으로 변환 합니다 **튜플** Visual Basic 튜플 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-219">The **ToTuple** method converts a Visual Basic tuple to a .NET **Tuple** object, and the **ToValueTuple** method converts a .NET **Tuple** object to a Visual Basic tuple.</span></span>

<span data-ttu-id="b8e9a-220">다음 예제에서는 튜플을 만듭니다,.NET으로 변환 **튜플** 개체 및 Visual Basic 튜플을 다시 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-220">The following example creates a tuple, converts it to a .NET **Tuple** object, and converts it back to a Visual Basic tuple.</span></span> <span data-ttu-id="b8e9a-221">이 예제에서는이 튜플 같은지를 확인 하려면 원본 하나를 사용 하 여 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e9a-221">The example then compares this tuple with the original one to ensure that they are equal.</span></span>

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a><span data-ttu-id="b8e9a-222">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8e9a-222">See also</span></span>

- [<span data-ttu-id="b8e9a-223">Visual Basic 언어 참조</span><span class="sxs-lookup"><span data-stu-id="b8e9a-223">Visual Basic Language Reference</span></span>](index.md)
