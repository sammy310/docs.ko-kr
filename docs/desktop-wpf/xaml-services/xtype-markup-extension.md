---
title: x:Type 태그 확장
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: f75d4e30dc41bbce995e466466c96c1a2830949b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432637"
---
# <a name="xtype-markup-extension"></a><span data-ttu-id="a834e-102">x:Type 태그 확장</span><span class="sxs-lookup"><span data-stu-id="a834e-102">x:Type Markup Extension</span></span>

<span data-ttu-id="a834e-103">지정된 XAML 형식의 기본 형식인 CLR <xref:System.Type> 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-103">Supplies the CLR <xref:System.Type> object that is the underlying type for a specified XAML type.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="a834e-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="a834e-104">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Type prefix:typeNameValue}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="a834e-105">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="a834e-105">XAML Object Element Usage</span></span>

```xaml
<x:Type TypeName="prefix:typeNameValue"/>
```

## <a name="xaml-values"></a><span data-ttu-id="a834e-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="a834e-106">XAML Values</span></span>

|||
|-|-|
|`prefix`|<span data-ttu-id="a834e-107">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="a834e-107">Optional.</span></span> <span data-ttu-id="a834e-108">기본이 아닌 XAML 네임스페이스를 매핑하는 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-108">A prefix that maps a non-default XAML namespace.</span></span> <span data-ttu-id="a834e-109">접두사를 지정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-109">Specifying a prefix is frequently not necessary.</span></span> <span data-ttu-id="a834e-110">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a834e-110">See Remarks.</span></span>|
|`typeNameValue`|<span data-ttu-id="a834e-111">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-111">Required.</span></span> <span data-ttu-id="a834e-112">현재 기본 XAML 네임스페이스에 확인할 수 있는 형식 이름; 또는 제공된 경우 `prefix` 지정된 매핑된 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-112">A type name resolvable to the current default XAML namespace; or the specified mapped prefix if `prefix` is supplied.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a834e-113">설명</span><span class="sxs-lookup"><span data-stu-id="a834e-113">Remarks</span></span>

<span data-ttu-id="a834e-114">`x:Type` 태그 확장은 C# 연산자 또는 Microsoft Visual Basic의 `typeof()` `GetType` 연산자와 유사한 기능을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-114">The `x:Type` markup extension has a similar function to the `typeof()` operator in C# or the `GetType` operator in Microsoft Visual Basic.</span></span>

<span data-ttu-id="a834e-115">태그 `x:Type` 확장 형식은 형식을 <xref:System.Type>취하는 속성에 대해 문자열 변환 동작을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-115">The `x:Type` markup extension supplies a from-string conversion behavior for properties that take the type <xref:System.Type>.</span></span> <span data-ttu-id="a834e-116">입력은 XAML 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-116">The input is a XAML type.</span></span> <span data-ttu-id="a834e-117">입력 XAML 형식과 출력 <xref:System.Type> CLR 간의 관계는 <xref:System.Type> XAML 스키마 컨텍스트와 컨텍스트가 제공하는 <xref:System.Xaml.XamlType.UnderlyingType%2A> <xref:System.Xaml.XamlType> <xref:System.Xaml.XamlType> <xref:System.Windows.Markup.IXamlTypeResolver> 서비스를 기반으로 필요한 것을 찾은 후 출력이 입력의 출력이라는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-117">The relationship between the input XAML type and the output CLR <xref:System.Type> is that the output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input <xref:System.Xaml.XamlType>, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>

<span data-ttu-id="a834e-118">.NET XAML 서비스에서 이 태그 확장에 대한 처리는 클래스에 <xref:System.Windows.Markup.TypeExtension> 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-118">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.TypeExtension> class.</span></span>

<span data-ttu-id="a834e-119">특정 프레임워크 구현에서 값으로 <xref:System.Type> 사용할 일부 속성은 형식의 이름(형식의 `Name`문자열 값)을 직접 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-119">In specific framework implementations, some properties that take <xref:System.Type> as a value can accept the name of the type directly (the string value of the type `Name`).</span></span> <span data-ttu-id="a834e-120">그러나 이 동작을 구현하는 것은 복잡한 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-120">However, implementing this behavior is a complex scenario.</span></span> <span data-ttu-id="a834e-121">예제에서는 다음의 "WPF 사용 참고 사항" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a834e-121">For examples, see the "WPF Usage Notes" section that follows.</span></span>

<span data-ttu-id="a834e-122">특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-122">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="a834e-123">`x:Type` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 확장명 클래스의 <xref:System.Windows.Markup.TypeExtension> 값으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-123">The string token provided after the `x:Type` identifier string is assigned as the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> value of the underlying <xref:System.Windows.Markup.TypeExtension> extension class.</span></span> <span data-ttu-id="a834e-124">CLR 형식을 기반으로 하는 .NET XAML 서비스에 대한 기본 XAML 스키마 컨텍스트에서 이 <xref:System.Reflection.MemberInfo.Name%2A> 특성의 값은 원하는 <xref:System.Reflection.MemberInfo.Name%2A> 형식의 값이거나 기본이 아닌 XAML 네임스페이스 매핑에 대한 접두사가 앞에 오는 것을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-124">Under the default XAML schema context for .NET XAML Services, which is based on CLR types, the value of this attribute is either the <xref:System.Reflection.MemberInfo.Name%2A> of the desired type, or contains that <xref:System.Reflection.MemberInfo.Name%2A> preceded by a prefix for a non-default XAML namespace mapping.</span></span>

<span data-ttu-id="a834e-125">태그 `x:Type` 확장은 개체 요소 구문에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-125">The `x:Type` markup extension can be used in object element syntax.</span></span> <span data-ttu-id="a834e-126">이 경우 확장을 올바르게 초기화하려면 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 속성 값을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-126">In this case, specifying the value of the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> property is required to properly initialize the extension.</span></span>

<span data-ttu-id="a834e-127">`x:Type` 태그 확장을 자세한 특성으로 사용할 수도 있습니다. 그러나 이 사용은 일반적인 것이 아닙니다.`<object property="{x:Type TypeName=typeNameValue}" .../>`</span><span class="sxs-lookup"><span data-stu-id="a834e-127">The `x:Type` markup extension can also be used as a verbose attribute; however this use is not typical: `<object property="{x:Type TypeName=typeNameValue}" .../>`</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="a834e-128">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="a834e-128">WPF Usage Notes</span></span>

### <a name="default-xaml-namespace-and-type-mapping"></a><span data-ttu-id="a834e-129">기본 XAML 네임스페이스 및 유형 매핑</span><span class="sxs-lookup"><span data-stu-id="a834e-129">Default XAML Namespace and Type Mapping</span></span>

<span data-ttu-id="a834e-130">WPF 프로그래밍의 기본 XAML 네임스페이스에는 일반적인 XAML 시나리오에 필요한 대부분의 XAML 형식이 포함되어 있습니다. 따라서 XAML 형식 값을 참조할 때 접두사를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-130">The default XAML namespace for WPF programming contains most of the XAML types you need for typical XAML scenarios; therefore, you can often avoid prefixes when referencing XAML type values.</span></span> <span data-ttu-id="a834e-131">사용자 지정 어셈블리에서 형식을 참조하거나 WPF 어셈블리에 있지만 기본 XAML 네임스페이스에 매핑되지 않은 CLR 네임스페이스의 형식인 경우 접두사를 매핑해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-131">You might need to map a prefix if you are referencing a type from a custom assembly or for types that exist in a WPF assembly but are from a CLR namespace that was not mapped to the default XAML namespace.</span></span> <span data-ttu-id="a834e-132">접두사, XAML 네임스페이스 및 CLR 네임스페이스 매핑에 대한 자세한 내용은 [WPF XAML에 대한 XAML 네임스페이스 및 네임스페이스 매핑을](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a834e-132">For more information about prefixes, XAML namespaces, and mapping CLR namespaces, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>

### <a name="type-properties-that-support-typename-as-string"></a><span data-ttu-id="a834e-133">문자열로 형식 이름을 지원하는 형식 속성</span><span class="sxs-lookup"><span data-stu-id="a834e-133">Type Properties That Support Typename-as-String</span></span>

<span data-ttu-id="a834e-134">WPF는 <xref:System.Type> `x:Type` 태그 확장 사용을 요구하지 않고 형식의 일부 속성의 값을 지정할 수 있는 기술을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-134">WPF supports techniques that enable specifying the value of some properties of type <xref:System.Type> without requiring an `x:Type` markup extension usage.</span></span> <span data-ttu-id="a834e-135">대신 형식을 이름을 지정하는 문자열로 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-135">Instead, you can specify the value as a string that names the type.</span></span> <span data-ttu-id="a834e-136">이 예는 <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> 다음과 <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>같습니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-136">Examples of this are <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> and <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a834e-137">이 동작에 대 한 지원 형식 변환기 또는 태그 확장을 통해 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-137">Support for this behavior is not provided through either type converters or markup extensions.</span></span> <span data-ttu-id="a834e-138">대신 을 통해 <xref:System.Windows.FrameworkElementFactory>구현된 지연 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-138">Instead, this is a deferral behavior implemented through <xref:System.Windows.FrameworkElementFactory>.</span></span>

<span data-ttu-id="a834e-139">실버라이트는 유사한 규칙을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-139">Silverlight supports a similar convention.</span></span> <span data-ttu-id="a834e-140">실제로 Silverlight는 현재 XAML 언어 지원에서 지원하지 `{x:Type}` 않으며 `{x:Type}` WPF-Silverlight XAML 마이그레이션을 지원하기 위한 몇 가지 상황 이외에는 사용을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-140">In fact, Silverlight does not currently support `{x:Type}` in its XAML language support, and does not accept `{x:Type}` usages outside of a few circumstances that are intended to support WPF-Silverlight XAML migration.</span></span> <span data-ttu-id="a834e-141">따라서 문자열로 형식 이름 동작은 값이 <xref:System.Type> 되는 모든 Silverlight 네이티브 속성 평가에 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-141">Therefore, the typename-as-string behavior is built-in to all Silverlight native property evaluation where a <xref:System.Type> is the value.</span></span>

## <a name="xaml-2009"></a><span data-ttu-id="a834e-142">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="a834e-142">XAML 2009</span></span>

<span data-ttu-id="a834e-143">XAML 2009는 제네릭 형식에 대한 추가 `x:TypeArguments` 지원을 `x:Type` 제공하고 기능 동작을 수정하고 이 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-143">XAML 2009 provides additional support for generic types and modifies the feature behavior of `x:TypeArguments` and `x:Type` to provide this support.</span></span>

- <span data-ttu-id="a834e-144">`x:TypeArguments`일반 개체 인스턴스화에 대한 연결된 개체 요소는 루트가 아닌 다른 요소에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-144">`x:TypeArguments` and the associated object element for a generic object instantiation can be on elements other than the root.</span></span> <span data-ttu-id="a834e-145">자세한 내용은 [x:TypeArguments 지시문](xtypearguments-directive.md)에서 "XAML 2009" 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a834e-145">For more information, see the "XAML 2009" section of [x:TypeArguments Directive](xtypearguments-directive.md).</span></span>

- <span data-ttu-id="a834e-146">XAML 2009는 태그에서 제네릭 형식의 제약 조건을 지정하기 위한 구문을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-146">XAML 2009 supports a syntax for specifying a generic type's constraint in markup.</span></span> <span data-ttu-id="a834e-147">이 기능은 `x:TypeArguments`에서 `x:Type`또는 두 기능을 조합하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-147">This can be used by `x:TypeArguments`, by `x:Type`, or by the two features in combination.</span></span>

- <span data-ttu-id="a834e-148">부하에 대한 XAML 2009를 처리할 때 WPF XAML 구현은 형식을 <xref:System.Type>사용하는 특정 프레임워크 속성에 대한 암시적 형식 변환 동작에 이 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-148">WPF XAML implementation when processing XAML 2009 for load also adds this capability to the implicit type conversion behavior for certain framework properties that use type <xref:System.Type>.</span></span>

<span data-ttu-id="a834e-149">WPF에서는 XAML 2009 기능을 사용할 수 있지만 느슨한 XAML(마크업 컴파일되지 않은 XAML)에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-149">In WPF, you can use XAML 2009 features but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="a834e-150">WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a834e-150">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>

## <a name="see-also"></a><span data-ttu-id="a834e-151">참조</span><span class="sxs-lookup"><span data-stu-id="a834e-151">See also</span></span>

- <xref:System.Windows.Style>
- [<span data-ttu-id="a834e-152">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="a834e-152">Styling and Templating</span></span>](../fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a834e-153">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="a834e-153">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
- [<span data-ttu-id="a834e-154">태그 확장명 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="a834e-154">Markup Extensions and WPF XAML</span></span>](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
