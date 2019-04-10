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
ms.openlocfilehash: eb0adb2e8140b20c8d52eced02f177b8c3560354
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211636"
---
# <a name="xtype-markup-extension"></a><span data-ttu-id="d1f33-102">x:Type 태그 확장</span><span class="sxs-lookup"><span data-stu-id="d1f33-102">x:Type Markup Extension</span></span>
<span data-ttu-id="d1f33-103">CLR 제공 <xref:System.Type> 개체는 지정된 된 XAML 형식에 대 한 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-103">Supplies the CLR <xref:System.Type> object that is the underlying type for a specified XAML type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="d1f33-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="d1f33-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="d1f33-105">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="d1f33-105">XAML Object Element Usage</span></span>  
  
```xaml  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="d1f33-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="d1f33-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`prefix`|<span data-ttu-id="d1f33-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-107">Optional.</span></span> <span data-ttu-id="d1f33-108">기본이 아닌 XAML 네임 스페이스에 매핑되는 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-108">A prefix that maps a non-default XAML namespace.</span></span> <span data-ttu-id="d1f33-109">접두사 지정 자주 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-109">Specifying a prefix is frequently not necessary.</span></span> <span data-ttu-id="d1f33-110">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1f33-110">See Remarks.</span></span>|  
|`typeNameValue`|<span data-ttu-id="d1f33-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="d1f33-111">Required.</span></span> <span data-ttu-id="d1f33-112">현재 기본 XAML 네임 스페이스; 확인할 수 있는 형식 이름 지정 된 접두사 경우 매핑됩니다 또는 `prefix` 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-112">A type name resolvable to the current default XAML namespace; or the specified mapped prefix if `prefix` is supplied.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1f33-113">설명</span><span class="sxs-lookup"><span data-stu-id="d1f33-113">Remarks</span></span>  
 <span data-ttu-id="d1f33-114">합니다 `x:Type` 태그 확장에는 비슷한 기능을 합니다 `typeof()` C# 연산자 또는 `GetType` Microsoft Visual Basic의 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-114">The `x:Type` markup extension has a similar function to the `typeof()` operator in C# or the `GetType` operator in Microsoft Visual Basic.</span></span>  
  
 <span data-ttu-id="d1f33-115">합니다 `x:Type` 형식을 사용 하는 속성에 대 한 문자열에서 변환 동작을 제공 하는 태그 확장 <xref:System.Type>합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-115">The `x:Type` markup extension supplies a from-string conversion behavior for properties that take the type <xref:System.Type>.</span></span> <span data-ttu-id="d1f33-116">입력은 XAML 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-116">The input is a XAML type.</span></span> <span data-ttu-id="d1f33-117">입력된 XAML 형식 및 CLR 출력 간의 관계 <xref:System.Type> 출력은 <xref:System.Type> 은 합니다 <xref:System.Xaml.XamlType.UnderlyingType%2A> 입력 <xref:System.Xaml.XamlType>, 필요한 조회 후 <xref:System.Xaml.XamlType> 기반으로 XAML 스키마 컨텍스트 및 합니다 <xref:System.Windows.Markup.IXamlTypeResolver>서비스 컨텍스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-117">The relationship between the input XAML type and the output CLR <xref:System.Type> is that the output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input <xref:System.Xaml.XamlType>, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="d1f33-118">.NET Framework XAML 서비스에서이 태그 확장에 대 한 처리에서 정의 됩니다는 <xref:System.Windows.Markup.TypeExtension> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-118">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.TypeExtension> class.</span></span>  
  
 <span data-ttu-id="d1f33-119">특정 프레임 워크 구현에서는 일부 속성을 수행할 <xref:System.Type> 으로 값 형식 이름의 직접 수락할 수 있습니다 (형식의 문자열 값 `Name`).</span><span class="sxs-lookup"><span data-stu-id="d1f33-119">In specific framework implementations, some properties that take <xref:System.Type> as a value can accept the name of the type directly (the string value of the type `Name`).</span></span> <span data-ttu-id="d1f33-120">그러나이 동작을 구현 복잡 한 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-120">However, implementing this behavior is a complex scenario.</span></span> <span data-ttu-id="d1f33-121">예를 들어 다음에 나오는 "WPF 사용 정보" 섹션을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-121">For examples, see the "WPF Usage Notes" section that follows.</span></span>  
  
 <span data-ttu-id="d1f33-122">특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-122">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="d1f33-123">`x:Type` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 확장 클래스의 <xref:System.Windows.Markup.TypeExtension> 값으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-123">The string token provided after the `x:Type` identifier string is assigned as the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> value of the underlying <xref:System.Windows.Markup.TypeExtension> extension class.</span></span> <span data-ttu-id="d1f33-124">이 특성의 값은 CLR 형식에 따라.NET Framework XAML 서비스에 대 한 기본 XAML 스키마 컨텍스트에서 <xref:System.Reflection.MemberInfo.Name%2A> 원하는 형식의 포함 또는 <xref:System.Reflection.MemberInfo.Name%2A> 앞에 기본이 아닌 XAML 네임 스페이스에 대 한 접두사 매핑입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-124">Under the default XAML schema context for .NET Framework XAML Services, which is based on CLR types, the value of this attribute is either the <xref:System.Reflection.MemberInfo.Name%2A> of the desired type, or contains that <xref:System.Reflection.MemberInfo.Name%2A> preceded by a prefix for a non-default XAML namespace mapping.</span></span>  
  
 <span data-ttu-id="d1f33-125">`x:Type` 개체 요소 구문에서 태그 확장을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-125">The `x:Type` markup extension can be used in object element syntax.</span></span> <span data-ttu-id="d1f33-126">이 경우 값을 지정 하는 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 제대로 확장을 초기화 하기 위해 속성이 필요한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-126">In this case, specifying the value of the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> property is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="d1f33-127">그러나 `x:Type` 이 사용 하이 여 일반적이 지; 태그 확장 자세한 정보를 특성으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-127">The `x:Type` markup extension can also be used as a verbose attribute; however this use is not typical:</span></span> `<object property="{x:Type TypeName=typeNameValue}" .../>`  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="d1f33-128">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="d1f33-128">WPF Usage Notes</span></span>  
  
### <a name="default-xaml-namespace-and-type-mapping"></a><span data-ttu-id="d1f33-129">기본 XAML Namespace 및 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="d1f33-129">Default XAML Namespace and Type Mapping</span></span>  
 <span data-ttu-id="d1f33-130">WPF 프로그래밍에 대 한 기본 XAML 네임 스페이스는 대부분의 일반적인 XAML 시나리오에 필요한 XAML 형식이 포함 따라서 XAML 형식 값을 참조할 때 접두사를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-130">The default XAML namespace for WPF programming contains most of the XAML types you need for typical XAML scenarios; therefore, you can often avoid prefixes when referencing XAML type values.</span></span> <span data-ttu-id="d1f33-131">또는 기본 XAML 네임 스페이스에 매핑되지 않은 CLR 네임 스페이스에서 있지만 WPF 어셈블리에 포함 된 형식에 대 한 사용자 지정 어셈블리에서 형식을 참조 하는 경우 접두사를 매핑할 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-131">You might need to map a prefix if you are referencing a type from a custom assembly or for types that exist in a WPF assembly but are from a CLR namespace that was not mapped to the default XAML namespace.</span></span> <span data-ttu-id="d1f33-132">매핑 CLR 네임 스페이스의 XAML 네임 스페이스 및 접두사에 대 한 자세한 내용은 참조 하세요. [XAML 네임 스페이스 및 WPF XAML에 대 한 매핑을 Namespace](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-132">For more information about prefixes, XAML namespaces, and mapping CLR namespaces, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
### <a name="type-properties-that-support-typename-as-string"></a><span data-ttu-id="d1f33-133">해당 지원 Typename 문자열로 속성 입력</span><span class="sxs-lookup"><span data-stu-id="d1f33-133">Type Properties That Support Typename-as-String</span></span>  
 <span data-ttu-id="d1f33-134">WPF 형식의 일부 속성의 값을 지정할 수 있는 기술을 지 원하는 <xref:System.Type> 없이 `x:Type` 태그 확장을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-134">WPF supports techniques that enable specifying the value of some properties of type <xref:System.Type> without requiring an `x:Type` markup extension usage.</span></span> <span data-ttu-id="d1f33-135">대신 형식 이름을 문자열로 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-135">Instead, you can specify the value as a string that names the type.</span></span> <span data-ttu-id="d1f33-136">이 예가 <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> 고 <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-136">Examples of this are <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> and <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d1f33-137">형식 변환기 또는 태그 확장을 통해이 동작에 대 한 지원을 제공 하지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-137">Support for this behavior is not provided through either type converters or markup extensions.</span></span> <span data-ttu-id="d1f33-138">대신,이 지연 동작을 통해 구현 <xref:System.Windows.FrameworkElementFactory>합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-138">Instead, this is a deferral behavior implemented through <xref:System.Windows.FrameworkElementFactory>.</span></span>  
  
 <span data-ttu-id="d1f33-139">Silverlight는 비슷한 규칙을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-139">Silverlight supports a similar convention.</span></span> <span data-ttu-id="d1f33-140">사실 Silverlight 현재 지원 하지 않습니다 `{x:Type}` XAML 언어 지원, 받아들이지 않는 및 `{x:Type}` WPF Silverlight XAML 마이그레이션을 지원 하기 위한 몇 가지 환경 외부에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-140">In fact, Silverlight does not currently support `{x:Type}` in its XAML language support, and does not accept `{x:Type}` usages outside of a few circumstances that are intended to support WPF-Silverlight XAML migration.</span></span> <span data-ttu-id="d1f33-141">따라서 문자열로 typename 동작은 모든 Silverlight 네이티브 속성 평가에 기본 제공 되는 <xref:System.Type> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-141">Therefore, the typename-as-string behavior is built-in to all Silverlight native property evaluation where a <xref:System.Type> is the value.</span></span>  
  
## <a name="xaml-2009"></a><span data-ttu-id="d1f33-142">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="d1f33-142">XAML 2009</span></span>  
 <span data-ttu-id="d1f33-143">제네릭 형식 및 기능 동작을 수정에 대 한 추가 지원을 제공 하는 XAML 2009 `x:TypeArguments` 및 `x:Type` 이 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-143">XAML 2009 provides additional support for generic types and modifies the feature behavior of `x:TypeArguments` and `x:Type` to provide this support.</span></span>  
  
-   `x:TypeArguments` <span data-ttu-id="d1f33-144">및의 관련된 개체 요소를 제네릭 개체 인스턴스화에 대 한 루트 이외의 요소에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-144">and the associated object element for a generic object instantiation can be on elements other than the root.</span></span> <span data-ttu-id="d1f33-145">자세한 내용은의 "XAML 2009" 섹션을 참조 하세요 [X:typearguments Directive](x-typearguments-directive.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-145">For more information, see the "XAML 2009" section of [x:TypeArguments Directive](x-typearguments-directive.md).</span></span>  
  
-   <span data-ttu-id="d1f33-146">XAML 2009 태그에서 제네릭 형식의 제약 조건을 지정 하는 구문을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-146">XAML 2009 supports a syntax for specifying a generic type's constraint in markup.</span></span> <span data-ttu-id="d1f33-147">사용할 수 있습니다 `x:TypeArguments`, `x:Type`, 또는 두 기능을 조합 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-147">This can be used by `x:TypeArguments`, by `x:Type`, or by the two features in combination.</span></span>  
  
-   <span data-ttu-id="d1f33-148">WPF XAML 구현 에서도 부하 유형을 사용 하는 특정 프레임 워크에 대 한 암시적 형식 변환 동작에이 기능을 추가 대 한 XAML 2009를 처리할 때 <xref:System.Type>합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-148">WPF XAML implementation when processing XAML 2009 for load also adds this capability to the implicit type conversion behavior for certain framework properties that use type <xref:System.Type>.</span></span>  
  
 <span data-ttu-id="d1f33-149">Wpf에서 느슨한 XAML (태그 컴파일되지 않은 XAML)의 경우에 XAML 2009 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-149">In WPF, you can use XAML 2009 features but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="d1f33-150">WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f33-150">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1f33-151">참고자료</span><span class="sxs-lookup"><span data-stu-id="d1f33-151">See also</span></span>

- <xref:System.Windows.Style>
- [<span data-ttu-id="d1f33-152">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="d1f33-152">Styling and Templating</span></span>](../wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="d1f33-153">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="d1f33-153">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="d1f33-154">태그 확장명 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="d1f33-154">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
