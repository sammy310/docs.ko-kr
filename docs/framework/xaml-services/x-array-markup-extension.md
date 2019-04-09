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
ms.openlocfilehash: 4f4e26eb3e5ccaf66b2173c7fc9952375c5f2a58
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139141"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="6f489-102">x:Array 태그 확장</span><span class="sxs-lookup"><span data-stu-id="6f489-102">x:Array Markup Extension</span></span>
<span data-ttu-id="6f489-103">XAML 태그 확장을 통해 개체의 배열에 대 한 일반 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="6f489-104">이에 해당 합니다 `x:ArrayExtension` [MS XAML]에서 XAML 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="6f489-105">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="6f489-105">XAML Object Element Usage</span></span>  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="6f489-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="6f489-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`typeName`|<span data-ttu-id="6f489-107">형식의 이름을 프로그램 `x:Array` 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-107">The name of the type that your `x:Array` will contain.</span></span> `typeName` <span data-ttu-id="6f489-108">수 있습니다 (그리고 종종 경우)를 XAML에 대 한 접두사가 네임 스페이스는 XAML을 포함 하는 형식 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-108">may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|  
|`arrayContents`|<span data-ttu-id="6f489-109">내장 함수에 할당 되는 항목 내용을 `ArrayExtension.Items` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="6f489-110">내에 포함 된 하나 이상의 개체 요소로 이러한 항목을 지정 하는 일반적으로 `x:Array` 태그 및 닫는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="6f489-111">여기에 지정 된 XAML 형식에 할당할 것으로 예상 되는 개체가 지정 `typeName`합니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f489-112">설명</span><span class="sxs-lookup"><span data-stu-id="6f489-112">Remarks</span></span>  
 `Type` <span data-ttu-id="6f489-113">모든 필수 특성은 `x:Array` 개체 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-113">is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="6f489-114">A `Type` 매개 변수 값을 사용 하지 않아도 `x:Type` 태그 확장; 단기 형식의 이름은 XAML 형식을 문자열로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>  
  
 <span data-ttu-id="6f489-115">.NET Framework XAML 서비스 구현에서 XAML 입력 및 출력 CLR 간의 관계 <xref:System.Type> 만든 배열의 영향을 받습니다 태그 확장에 대 한 서비스 컨텍스트.</span><span class="sxs-lookup"><span data-stu-id="6f489-115">In the .NET Framework XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="6f489-116">출력 <xref:System.Type> 은 합니다 <xref:System.Xaml.XamlType.UnderlyingType%2A> 필요한 조회 후 입력 XAML 형식의 <xref:System.Xaml.XamlType> XAML 스키마 컨텍스트를 기반으로 및 <xref:System.Windows.Markup.IXamlTypeResolver> 서비스 컨텍스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="6f489-117">배열 콘텐츠가에 할당 된 처리 될 때를 `ArrayExtension.Items` 내장 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="6f489-118">에 <xref:System.Windows.Markup.ArrayExtension> 구현에서이 표현 됩니다 <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="6f489-119">이 태그 확장에 대 한 처리 정의한.NET Framework XAML 서비스 구현에서의 <xref:System.Windows.Markup.ArrayExtension> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-119">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <xref:System.Windows.Markup.ArrayExtension> <span data-ttu-id="6f489-120">봉인 되지 및 사용자 지정 배열 형식에 대 한 태그 확장 구현에 대 한 기준으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-120">is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>  
  
 `x:Array` <span data-ttu-id="6f489-121">자세한 내용은 위한 일반 XAML 언어 확장성입니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-121">is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="6f489-122">하지만 `x:Array` XAML 구조적된 속성 내용으로 XAML에서 지 원하는 컬렉션을 사용 하는 특정 속성 값을 지정 하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="6f489-123">예를 들어의 콘텐츠를 지정할 수 있습니다는 <xref:System.Collections.IEnumerable> 속성과 `x:Array` 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>  
  
 `x:Array` <span data-ttu-id="6f489-124">태그 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-124">is a markup extension.</span></span> <span data-ttu-id="6f489-125">태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> `x:Array` <span data-ttu-id="6f489-126">이므로 부분적으로 해당 규칙의 예외는 대체 특성 값 처리를 제공 하는 대신 `x:Array` 의 내부 텍스트 내용을 처리 대안을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-126">is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="6f489-127">이 동작을 통해 배열에 그룹화 되어; 명명 된 배열에 액세스 하 여 코드 숨김의 뒷부분에 나오는 참조 기존 콘텐츠 모델에서 지원 될 수 있는 형식 호출할 수 있습니다 <xref:System.Array> 메서드 개별 배열 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>  
  
 <span data-ttu-id="6f489-128">XAML의 모든 태그 확장 사용은 중괄호 ({,} `)` 는 XAML 프로세서는 태그 확장 특성 값을 처리 해야 한다는 것을 인식 하는 규칙은 특성 구문에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="6f489-129">태그 확장에에서 대 한 자세한 내용은 참조 하세요. [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions-for-xaml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions-for-xaml.md).</span></span>  
  
 <span data-ttu-id="6f489-130">XAML 2009 년 `x:Array` 언어 태그 확장 하는 대신 기본 형식으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="6f489-131">자세한 내용은 [공용 XAML 언어 기본 형식에 대 한 기본 제공 형식](built-in-types-for-common-xaml-language-primitives.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-131">For more information, see [Built-in Types for Common XAML Language Primitives](built-in-types-for-common-xaml-language-primitives.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="6f489-132">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="6f489-132">WPF Usage Notes</span></span>  
 <span data-ttu-id="6f489-133">채우는 개체 요소를 일반적으로 `x:Array` 에 존재 하는 요소가 없는 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML 네임 스페이스에 기본이 아닌 XAML 네임 스페이스 접두사 매핑이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>  
  
 <span data-ttu-id="6f489-134">예를 들어, 다음 된 두 문자열의 간단한 배열 합니다 `sys` 접두사 (그리고 `x`) 배열 수준에서 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>  
  
 <span data-ttu-id="6f489-135">[xaml]</span><span class="sxs-lookup"><span data-stu-id="6f489-135">[xaml]</span></span>  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 <span data-ttu-id="6f489-136">배열 요소로 사용 되는 사용자 지정 형식에 대 한 클래스는 XAML 개체 요소로 인스턴스화되는 것에 대 한 요구 사항을 지원도 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-136">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="6f489-137">자세한 내용은 [XAML 및 WPF에 대 한 사용자 지정 클래스](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6f489-137">For more information, see [XAML and Custom Classes for WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f489-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="6f489-138">See also</span></span>

- [<span data-ttu-id="6f489-139">태그 확장명 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="6f489-139">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="6f489-140">WPF에서 System.Xaml로 마이그레이션된 형식</span><span class="sxs-lookup"><span data-stu-id="6f489-140">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
