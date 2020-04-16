---
title: XAML의 제네릭
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: 9354f74b978652c36df28a91a6b9db5cfff4bb1e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432961"
---
# <a name="generics-in-xaml"></a><span data-ttu-id="72417-102">XAML의 제네릭</span><span class="sxs-lookup"><span data-stu-id="72417-102">Generics in XAML</span></span>

<span data-ttu-id="72417-103">구현된 <xref:System.Xaml?displayProperty=fullName> .NET XAML 서비스는 제네릭 CLR 형식을 사용할 수 있는 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="72417-103">.NET XAML Services as implemented in <xref:System.Xaml?displayProperty=fullName> provides support for using generic CLR types.</span></span> <span data-ttu-id="72417-104">이 지원에는 제네릭의 제약 조건을 형식 인수로 지정하고 제네릭 컬렉션 사례에 적합한 `Add` 메서드를 호출하여 제약 조건을 적용하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="72417-104">This support includes specifying the constraints of generics as a type argument and enforcing the constraint by calling the appropriate `Add` method for generic collection cases.</span></span> <span data-ttu-id="72417-105">이 항목에서는 XAML에서 제네릭 형식을 사용하고 참조하는 측면에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72417-105">This topic describes aspects of using and referencing generic types in XAML.</span></span>

## <a name="xtypearguments"></a><span data-ttu-id="72417-106">x:타자 인수</span><span class="sxs-lookup"><span data-stu-id="72417-106">x:TypeArguments</span></span>

<span data-ttu-id="72417-107">`x:TypeArguments`은 XAML 언어로 정의된 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="72417-107">`x:TypeArguments` is a directive defined by the XAML language.</span></span> <span data-ttu-id="72417-108">제네릭 형식에 의해 지원되는 XAML 형식의 멤버로 `x:TypeArguments` 사용되는 경우 제네릭의 제한 형식 인수를 백업 생성자로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="72417-108">When it is used as a member of a XAML type that is backed by a generic type, `x:TypeArguments` passes constraining type arguments of the generic to the backing constructor.</span></span> <span data-ttu-id="72417-109">구문 예제를 포함하는 .NET XAML 서비스 사용과 `x:TypeArguments`관련된 참조 구문은 [x:TypeArguments 지시문을](xtypearguments-directive.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="72417-109">For reference syntax that pertains to .NET XAML Services use of `x:TypeArguments`, which includes syntax examples, see [x:TypeArguments Directive](xtypearguments-directive.md).</span></span>

<span data-ttu-id="72417-110">문자열을 사용 하 고 형식 변환기 백업을 사용 하기 때문에 `x:TypeArguments` 일반적으로 XAML 사용에서 특성으로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72417-110">Because `x:TypeArguments` takes a string, and has type converter backing, it is typically declared in XAML usage as an attribute.</span></span>

<span data-ttu-id="72417-111">XAML 노드 스트림에서, 선언된 `x:TypeArguments` 정보는 노드 <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> 스트림의 `StartObject` 위치에서 얻을 수 있다.</span><span class="sxs-lookup"><span data-stu-id="72417-111">In the XAML node stream, the information declared by `x:TypeArguments` can be obtained from <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> at a `StartObject` position in the node stream.</span></span> <span data-ttu-id="72417-112">반환 <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> 값은 <xref:System.Xaml.XamlType> 값 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="72417-112">The return value of <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> is a list of <xref:System.Xaml.XamlType> values.</span></span> <span data-ttu-id="72417-113">XAML 형식이 제네릭 형식을 나타내는지 여부를 <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>결정하는 것은 을 호출하여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72417-113">Determination of whether a XAML type represents a generic type can be made by calling <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>.</span></span>

## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a><span data-ttu-id="72417-114">XAML의 제네릭에 대한 규칙 및 구문 규칙</span><span class="sxs-lookup"><span data-stu-id="72417-114">Rules and Syntax Conventions for Generics in XAML</span></span>

<span data-ttu-id="72417-115">XAML에서 제네릭 형식은 항상 제한된 제네릭으로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72417-115">In XAML, a generic type must always be represented as a constrained generic.</span></span> <span data-ttu-id="72417-116">제한되지 않은 제네릭은 XAML 형식 시스템 또는 XAML 노드 스트림에 존재하지 않으며 XAML 태그에 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72417-116">An unconstrained generic is never present in the XAML type system or a XAML node stream and cannot be represented in XAML markup.</span></span> <span data-ttu-id="72417-117">제네릭은 에 의해 `x:TypeArguments`참조되는 제네릭의 중첩 형식 제약 조건인 경우 또는 제네릭 `x:Type` 형식에 대한 CLR 형식 참조를 제공하는 경우에 대해 XAML 특성 구문 내에서 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72417-117">A generic can be referenced within XAML attribute syntax for cases where it is a nested type constraint of a generic being referenced by `x:TypeArguments`, or for cases where `x:Type` supplies a CLR type reference for a generic type.</span></span> <span data-ttu-id="72417-118">제네릭 참조는 .NET <xref:System.Xaml.Schema.XamlTypeTypeConverter> XAML 서비스에서 정의한 클래스를 통해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="72417-118">Referencing generics is supported through the <xref:System.Xaml.Schema.XamlTypeTypeConverter> class defined by .NET XAML Services.</span></span>

<span data-ttu-id="72417-119">제네릭의 형식 및 제약 <xref:System.Xaml.Schema.XamlTypeTypeConverter> 조건에 대해 각도 대괄호를 사용하는 일반적인 MSIL/CLR 구문 규칙을 변경하고 대신 제약 조건 컨테이너에 대한 괄호를 대체하는 XAML 특성 구문 양식입니다.</span><span class="sxs-lookup"><span data-stu-id="72417-119">The XAML attribute syntax form enabled by <xref:System.Xaml.Schema.XamlTypeTypeConverter> alters the typical MSIL / CLR syntax convention that uses angle brackets for types and constraints of generics, and instead substitutes parentheses for the constraint container.</span></span> <span data-ttu-id="72417-120">예를 들어 [x:TypeArguments 지시문을](xtypearguments-directive.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="72417-120">For an example, see [x:TypeArguments Directive](xtypearguments-directive.md).</span></span>

## <a name="generics-and-xaml-2009-features"></a><span data-ttu-id="72417-121">제네릭 및 XAML 2009 기능</span><span class="sxs-lookup"><span data-stu-id="72417-121">Generics and XAML 2009 Features</span></span>

<span data-ttu-id="72417-122">CLR 기본 형식을 매핑하는 대신 XAML 2009를 사용하여 공통 언어 기본 항목에 대한 XAML 형식을 가져오는 경우 [XAML 2009 기본](types-for-primitives.md) 제공 형식을 정보 항목으로 사용할 수 `x:TypeArguments`있습니다.</span><span class="sxs-lookup"><span data-stu-id="72417-122">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [XAML 2009 built-in types](types-for-primitives.md) as information items in `x:TypeArguments`.</span></span> <span data-ttu-id="72417-123">예를 들어 다음을 선언할 수 있습니다(접두사 `x` 매핑은 표시되지 않지만 XAML 2009의 XAML 언어 XAML 네임스페이스는).</span><span class="sxs-lookup"><span data-stu-id="72417-123">For example, you could declare the following (prefix mappings not shown, but `x` is the XAML language XAML namespace for XAML 2009):</span></span>

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

## <a name="generics-support-in-wpf"></a><span data-ttu-id="72417-124">WPF의 제네릭 지원</span><span class="sxs-lookup"><span data-stu-id="72417-124">Generics Support in WPF</span></span>

<span data-ttu-id="72417-125">WPF를 구체적으로 대상으로 삼을 때 XAML 2006 사용의 경우 `x:TypeArguments` [x:Class도](xclass-directive.md) 와 동일한 요소에 제공되어야 하며 해당 요소는 XAML 문서의 루트 요소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72417-125">For XAML 2006 usage when specifically targeting WPF, [x:Class](xclass-directive.md) must also be provided on the same element as `x:TypeArguments`, and that element must be the root element in a XAML document.</span></span> <span data-ttu-id="72417-126">루트 요소는 하나 이상의 형식 인수를 가진 제네릭 형식에 매핑되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72417-126">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="72417-127">예제는 <xref:System.Windows.Navigation.PageFunction%601>입니다.</span><span class="sxs-lookup"><span data-stu-id="72417-127">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span>

<span data-ttu-id="72417-128">제네릭 사용을 지원하는 가능한 해결 방법으로는 제네릭 형식을 반환할 수 있는 사용자 지정 태그 확장 정의 또는 제네릭 형식에서 파생되지만 자체 클래스 정의에서 제네릭 제약 조건을 병합하는 래핑 클래스 정의 제공등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72417-128">Possible workarounds to support generic usages include defining a custom markup extension that can return generic types, or providing a wrapping class definition that derives from a generic type but flattens the generic constraint in its own class definition.</span></span>

<span data-ttu-id="72417-129">WPF에서는 XAML 2009 기능을 함께 `x:TypeArguments`사용할 수 있지만 느슨한 XAML(마크업 컴파일되지 않은 XAML)에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72417-129">In WPF you can use XAML 2009 features together with `x:TypeArguments`, but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="72417-130">WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72417-130">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>

<span data-ttu-id="72417-131">.NET Framework 3.5에 대한 Windows 워크플로 재단의 사용자 지정 워크플로는 일반 XAML 사용을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72417-131">Custom workflows in Windows Workflow Foundation for .NET Framework 3.5 do not support generic XAML usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="72417-132">참조</span><span class="sxs-lookup"><span data-stu-id="72417-132">See also</span></span>

- [<span data-ttu-id="72417-133">x:TypeArguments 지시문</span><span class="sxs-lookup"><span data-stu-id="72417-133">x:TypeArguments Directive</span></span>](xtypearguments-directive.md)
- [<span data-ttu-id="72417-134">x:Class 지시문</span><span class="sxs-lookup"><span data-stu-id="72417-134">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="72417-135">공용 XAML 언어 기본 형식에 대한 기본 제공 형식</span><span class="sxs-lookup"><span data-stu-id="72417-135">Built-in Types for Common XAML Language Primitives</span></span>](types-for-primitives.md)
