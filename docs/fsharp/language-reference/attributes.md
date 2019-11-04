---
title: 특성
description: 특성을 F# 사용 하 여 프로그래밍 구문에 메타 데이터를 적용 하는 방법을 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 223263f5789b0fc7eb2b3ef2905f6436980bd14a
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424792"
---
# <a name="attributes"></a><span data-ttu-id="a6a03-103">특성</span><span class="sxs-lookup"><span data-stu-id="a6a03-103">Attributes</span></span>

<span data-ttu-id="a6a03-104">특성을 사용 하면 프로그래밍 구문에 메타 데이터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-104">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="a6a03-105">구문</span><span class="sxs-lookup"><span data-stu-id="a6a03-105">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="a6a03-106">주의</span><span class="sxs-lookup"><span data-stu-id="a6a03-106">Remarks</span></span>

<span data-ttu-id="a6a03-107">이전 구문에서 *대상은* 선택 사항이 며, 있는 경우 특성이 적용 되는 프로그램 엔터티의 종류를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-107">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="a6a03-108">*대상* 에 유효한 값은이 문서의 뒷부분에 나오는 표에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-108">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="a6a03-109">*특성 이름* 은 특성 형식 이름에 일반적으로 사용 되는 `Attribute` 접미사를 사용 하거나 사용 하지 않고 유효한 특성 형식의 이름 (네임 스페이스로 한정 될 수 있음)을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-109">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="a6a03-110">예를 들어 `ObsoleteAttribute` 형식은이 컨텍스트에서 `Obsolete`만 단축 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-110">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="a6a03-111">*인수* 는 특성 형식의 생성자에 대 한 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-111">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="a6a03-112">특성에 매개 변수가 없는 생성자가 있는 경우 인수 목록과 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-112">If an attribute has a parameterless constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="a6a03-113">특성은 위치 인수와 명명 된 인수를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-113">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="a6a03-114">*위치 인수* 는 표시 되는 순서 대로 사용 되는 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-114">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="a6a03-115">특성에 public 속성이 있는 경우 명명 된 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-115">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="a6a03-116">인수 목록에서 다음 구문을 사용 하 여이를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-116">You can set these by using the following syntax in the argument list.</span></span>

```fsharp
property-name = property-value
```

<span data-ttu-id="a6a03-117">이러한 속성 초기화는 순서에 제한이 없지만 위치 인수를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-117">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="a6a03-118">다음은 위치 인수 및 속성 초기화를 사용 하는 특성의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-118">The following is an example of an attribute that uses positional arguments and property initializations:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="a6a03-119">이 예제에서 특성은 `DllImportAttribute`되며, 여기서는 약식으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-119">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="a6a03-120">첫 번째 인수는 위치 매개 변수이 고, 두 번째 인수는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-120">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="a6a03-121">특성은 *특성* 으로 알려진 개체가 형식 또는 다른 프로그램 요소와 연결 될 수 있도록 하는 .net 프로그래밍 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-121">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="a6a03-122">특성이 적용 되는 program 요소를 *특성 대상*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-122">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="a6a03-123">특성은 일반적으로 대상에 대 한 메타 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-123">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="a6a03-124">이 컨텍스트에서 메타 데이터는 필드 및 멤버 이외의 형식에 대 한 모든 데이터가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-124">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="a6a03-125">의 F# 특성은 함수, 메서드, 어셈블리, 모듈, 형식 (클래스, 레코드, 구조체, 인터페이스, 대리자, 열거형, 공용 구조체 등), 생성자, 속성, 필드와 같은 프로그래밍 구문에 적용 될 수 있습니다. 매개 변수, 형식 매개 변수 및 반환 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-125">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="a6a03-126">클래스, 식 또는 워크플로 식 내의 `let` 바인딩에서는 특성을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-126">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="a6a03-127">일반적으로 특성 선언은 특성 대상의 선언 바로 앞에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-127">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="a6a03-128">다음과 같이 여러 특성 선언을 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-128">Multiple attribute declarations can be used together, as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="a6a03-129">.NET 리플렉션을 사용 하 여 런타임에 특성을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-129">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="a6a03-130">앞의 코드 예제와 같이 여러 특성을 개별적으로 선언 하거나, 세미콜론을 사용 하 여 개별 특성 및 생성자를 구분 하는 경우 한 개의 대괄호 집합에서 다음과 같이 여러 특성을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-130">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="a6a03-131">일반적으로 발생 하는 특성에는 `Obsolete` 특성, 보안 고려 사항에 대 한 특성, COM 지원에 대 한 특성, 코드의 소유권과 관련 된 특성, 형식을 serialize 할 수 있는지 여부를 나타내는 특성 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-131">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="a6a03-132">다음 예에서는 `Obsolete` 특성을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-132">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="a6a03-133">특성 대상 `assembly` 및 `module`의 경우 어셈블리의 최상위 `do` 바인딩에 특성을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-133">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="a6a03-134">다음과 같이 특성 선언에 `assembly` 또는 `module` 단어를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-134">You can include the word `assembly` or `module` in the attribute declaration, as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="a6a03-135">`do` 바인딩에 적용 된 특성에 대 한 특성 대상을 생략 하면 컴파일러는 F# 해당 특성에 적합 한 특성 대상을 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-135">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="a6a03-136">많은 특성 클래스에는 해당 특성에 대해 지원 되는 가능한 대상에 대 한 정보를 포함 하는 `System.AttributeUsageAttribute` 형식의 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-136">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="a6a03-137">`System.AttributeUsageAttribute` 특성에서 대상으로 함수를 지원함을 나타내는 경우에는 해당 특성이 프로그램의 주 진입점에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-137">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="a6a03-138">`System.AttributeUsageAttribute` 특성이 어셈블리를 대상으로 지원 함을 나타내는 경우 컴파일러는 특성을 사용 하 여 어셈블리에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="a6a03-139">대부분의 특성은 함수 및 어셈블리에 모두 적용 되지 않지만, 이러한 특성을 사용 하는 경우에는 프로그램의 main 함수에 특성을 적용 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-139">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="a6a03-140">특성 대상이 명시적으로 지정 된 경우 특성이 지정 된 대상에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-140">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="a6a03-141">일반적으로 특성 대상을 명시적으로 지정할 필요는 없지만 특성의 *target* 에 대 한 유효한 값을 사용 예제와 함께 사용 하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a03-141">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute along with examples of usage are shown in the following table:</span></span>

<table>
  <tr>
    <th><span data-ttu-id="a6a03-142">특성 대상</span><span class="sxs-lookup"><span data-stu-id="a6a03-142">Attribute target</span></span></td>
    <th><span data-ttu-id="a6a03-143">예제</span><span class="sxs-lookup"><span data-stu-id="a6a03-143">Example</span></span></td>
  </tr>
  <tr>
    <td><span data-ttu-id="a6a03-144">어셈블리(assembly)</span><span class="sxs-lookup"><span data-stu-id="a6a03-144">assembly</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="a6a03-145">반환값(return)</span><span class="sxs-lookup"><span data-stu-id="a6a03-145">return</span></span></td>
    <td><pre lang="fsharp"><code>let function1 x : [&lt;return: Obsolete&gt;] int = x + 1</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="a6a03-146">필드(field)</span><span class="sxs-lookup"><span data-stu-id="a6a03-146">field</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;field: DefaultValue&gt;] val mutable x: int</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="a6a03-147">속성(property)</span><span class="sxs-lookup"><span data-stu-id="a6a03-147">property</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;property: Obsolete&gt;] this.MyProperty = x</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="a6a03-148">매개변수(param)</span><span class="sxs-lookup"><span data-stu-id="a6a03-148">param</span></span></td>
    <td><pre lang="fsharp"><code>member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="a6a03-149">형식(type)</span><span class="sxs-lookup"><span data-stu-id="a6a03-149">type</span></span></td>
    <td>
        <pre lang="fsharp"><code>
[&lt;type: StructLayout(Sequential)&gt;]
type MyStruct =
struct
x : byte
y : int
end</code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="a6a03-150">참조</span><span class="sxs-lookup"><span data-stu-id="a6a03-150">See also</span></span>

- [<span data-ttu-id="a6a03-151">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="a6a03-151">F# Language Reference</span></span>](index.md)
