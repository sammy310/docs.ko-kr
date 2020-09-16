---
title: x:Array 태그 확장
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: b812939cbaa74576361de534c0d39ba45536cbcf
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555174"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="73c48-102">x:Array 태그 확장</span><span class="sxs-lookup"><span data-stu-id="73c48-102">x:Array Markup Extension</span></span>

<span data-ttu-id="73c48-103">태그 확장을 통해 XAML에서 개체의 배열을 일반적으로 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="73c48-104">이는 `x:ArrayExtension` [MS xaml]의 XAML 형식에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="73c48-105">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="73c48-105">XAML Object Element Usage</span></span>

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a><span data-ttu-id="73c48-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="73c48-106">XAML Values</span></span>

|||
|-|-|
|`typeName`|<span data-ttu-id="73c48-107">에 포함 될 형식의 이름입니다 `x:Array` .</span><span class="sxs-lookup"><span data-stu-id="73c48-107">The name of the type that your `x:Array` will contain.</span></span> <span data-ttu-id="73c48-108">`typeName` 는 XAML 형식 정의를 포함 하는 XAML 네임 스페이스를 접두사로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-108">`typeName` may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|
|`arrayContents`|<span data-ttu-id="73c48-109">내장 속성에 할당 된 항목 내용입니다 `ArrayExtension.Items` .</span><span class="sxs-lookup"><span data-stu-id="73c48-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="73c48-110">일반적으로 이러한 항목은 `x:Array` 여는 태그와 닫는 태그 내에 포함 된 하나 이상의 개체 요소로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="73c48-111">여기에 지정 된 개체는에 지정 된 XAML 형식에 할당할 수 있어야 `typeName` 합니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|

## <a name="remarks"></a><span data-ttu-id="73c48-112">설명</span><span class="sxs-lookup"><span data-stu-id="73c48-112">Remarks</span></span>

<span data-ttu-id="73c48-113">`Type` 는 모든 개체 요소에 대 한 필수 특성입니다 `x:Array` .</span><span class="sxs-lookup"><span data-stu-id="73c48-113">`Type` is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="73c48-114">`Type`매개 변수 값은 태그 확장을 사용할 필요가 없습니다 `x:Type` . 형식의 약식 이름은 문자열로 지정할 수 있는 XAML 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>

<span data-ttu-id="73c48-115">.NET XAML 서비스 구현에서 작성 된 배열의 입력 XAML 형식과 출력 CLR 간의 관계는 <xref:System.Type> 태그 확장에 대 한 서비스 컨텍스트의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-115">In .NET XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="73c48-116">출력은 <xref:System.Type> <xref:System.Xaml.XamlType.UnderlyingType%2A> <xref:System.Xaml.XamlType> xaml 스키마 컨텍스트 및 <xref:System.Windows.Markup.IXamlTypeResolver> 컨텍스트에서 제공 하는 서비스를 기반으로 필요한를 조회 한 후 입력 xaml 형식의입니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>

<span data-ttu-id="73c48-117">처리 되 면 배열 내용이 내장 속성에 할당 됩니다 `ArrayExtension.Items` .</span><span class="sxs-lookup"><span data-stu-id="73c48-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="73c48-118">구현에서 <xref:System.Windows.Markup.ArrayExtension> 이는로 표현 됩니다 <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="73c48-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="73c48-119">.NET XAML 서비스 구현에서이 태그 확장에 대 한 처리는 클래스에 의해 정의 됩니다 <xref:System.Windows.Markup.ArrayExtension> .</span><span class="sxs-lookup"><span data-stu-id="73c48-119">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <span data-ttu-id="73c48-120"><xref:System.Windows.Markup.ArrayExtension> 는 sealed가 아니고 사용자 지정 배열 형식에 대 한 태그 확장 구현의 기초로 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-120"><xref:System.Windows.Markup.ArrayExtension> is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>

<span data-ttu-id="73c48-121">`x:Array` 는 XAML에서 일반적인 언어 확장성을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-121">`x:Array` is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="73c48-122">그러나는 `x:Array` xaml 지원 컬렉션을 구조화 된 속성 콘텐츠로 사용 하는 특정 속성의 xaml 값을 지정 하는 데 유용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="73c48-123">예를 들어 사용으로 속성의 내용을 지정할 수 있습니다 <xref:System.Collections.IEnumerable> `x:Array` .</span><span class="sxs-lookup"><span data-stu-id="73c48-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>

<span data-ttu-id="73c48-124">`x:Array`은 태그 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-124">`x:Array` is a markup extension.</span></span> <span data-ttu-id="73c48-125">태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="73c48-126">`x:Array` 는 대체 특성 값 처리를 제공 하는 대신 `x:Array` 내부 텍스트 콘텐츠의 대체 처리를 제공 하기 때문에이 규칙에 대 한 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-126">`x:Array` is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="73c48-127">이 동작을 사용 하면 기존 콘텐츠 모델에서 지원 되지 않는 형식을 배열로 그룹화 하 고 나중에 명명 된 배열에 액세스 하 여 코드 숨김으로 참조할 수 있습니다. <xref:System.Array> 메서드를 호출 하 여 개별 배열 항목을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>

<span data-ttu-id="73c48-128">XAML의 모든 태그 확장은 특성 구문에서 중괄호를 사용 합니다 {,} `)` .이는 xaml 프로세서가 태그 확장에서 특성 값을 처리 해야 함을 인식 하는 데 사용 되는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="73c48-129">일반적인 태그 확장에 대 한 자세한 내용은 [XAML의 형식 변환기 및 태그 확장명](type-converters-and-markup-extensions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73c48-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md).</span></span>

<span data-ttu-id="73c48-130">XAML 2009에서 `x:Array` 는 태그 확장 대신 언어 기본 형식으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="73c48-131">자세한 내용은 [일반적인 XAML 언어 기본 형식에 대 한 기본 제공 형식](types-for-primitives.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73c48-131">For more information, see [Built-in Types for Common XAML Language Primitives](types-for-primitives.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="73c48-132">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="73c48-132">WPF Usage Notes</span></span>

<span data-ttu-id="73c48-133">일반적으로를 채우는 개체 요소는 `x:Array` xaml 네임 스페이스에 존재 하는 요소가 아니라 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 기본 xaml 네임 스페이스에 대 한 접두사 매핑이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>

<span data-ttu-id="73c48-134">예를 들어 다음은 `sys` `x` 배열 수준에서 정의 된 접두사 (및)가 있는 두 문자열의 단순 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

<span data-ttu-id="73c48-135">배열 요소로 사용 되는 사용자 지정 형식의 경우 클래스가 XAML에서 개체 요소로 인스턴스화되기 위한 요구 사항도 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73c48-135">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="73c48-136">자세한 내용은 [WPF에 대 한 XAML 및 사용자 지정 클래스](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73c48-136">For more information, see [XAML and Custom Classes for WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf).</span></span>

## <a name="see-also"></a><span data-ttu-id="73c48-137">참조</span><span class="sxs-lookup"><span data-stu-id="73c48-137">See also</span></span>

- [<span data-ttu-id="73c48-138">태그 확장명 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="73c48-138">Markup Extensions and WPF XAML</span></span>](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
- [<span data-ttu-id="73c48-139">WPF에서 System.Xaml로 마이그레이션된 형식</span><span class="sxs-lookup"><span data-stu-id="73c48-139">Types Migrated from WPF to System.Xaml</span></span>](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
