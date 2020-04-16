---
title: x:XData 내장 XAML 형식
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: b7f0954158988db107feb4a6c51ba81d5db11dcb
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432793"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="25d8c-102">x:XData 내장 XAML 형식</span><span class="sxs-lookup"><span data-stu-id="25d8c-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="25d8c-103">XAML 프로덕션 내에서 XML 데이터 섬을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="25d8c-104">XAML `x:XData` 프로세서 내의 XML 요소는 작동 기본 XAML 네임스페이스 또는 다른 XAML 네임스페이스의 일부인 것처럼 처리해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="25d8c-105">`x:XData`임의의 잘 형성된 XML을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-105">`x:XData` can contain arbitrary well-formed XML.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="25d8c-106">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="25d8c-106">XAML Object Element Usage</span></span>

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a><span data-ttu-id="25d8c-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="25d8c-107">XAML Values</span></span>

|||
|-|-|
|`elementDataRoot`|<span data-ttu-id="25d8c-108">둘러싸인 데이터 섬의 단일 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="25d8c-109">대부분의 최종 소비자의 경우 단일 루트가 없는 XML은 유효하지 않은 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="25d8c-110">특히 WPF또는 데이터 바인딩을 `x:XData` 위해 XML 원본을 사용하는 다른 많은 기술에 대한 XML 데이터 원본으로 의도된 경우 단일 루트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|
|`[elementData]`|<span data-ttu-id="25d8c-111">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="25d8c-111">Optional.</span></span> <span data-ttu-id="25d8c-112">XML 데이터를 나타내는 XML입니다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-112">XML that represents the XML data.</span></span> <span data-ttu-id="25d8c-113">요소 데이터로 포함할 수 있는 요소 수와 중첩된 요소가 다른 요소에 포함될 수 있습니다. 그러나 XML의 일반 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|

## <a name="remarks"></a><span data-ttu-id="25d8c-114">설명</span><span class="sxs-lookup"><span data-stu-id="25d8c-114">Remarks</span></span>

<span data-ttu-id="25d8c-115">개체 내의 `x:XData` XML 요소는 데이터 내에 포함된 XMLDOM의 가능한 모든 네임스페이스 및 접두사를 다시 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>

<span data-ttu-id="25d8c-116">XML 데이터와 `x:XData` 본질적인 XAML 형식에 대한 프로그래밍 방식으로 클래스를 <xref:System.Windows.Markup.XData> 통해 .NET XAML 서비스에서 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="25d8c-117">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="25d8c-117">WPF Usage Notes</span></span>

<span data-ttu-id="25d8c-118">개체는 `x:XData` 주로 <xref:System.Windows.Data.XmlDataProvider>속성의 자식 개체(XAML에서 일반적으로 속성 요소 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 구문으로 표현)의 자식 개체또는 또는 다른 방법으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>

<span data-ttu-id="25d8c-119">데이터는 일반적으로 데이터 섬 내의 기본 XML 네임스페이스를 빈 문자열로 설정된 새 기본 XML 네임스페이스로 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="25d8c-120">데이터를 참조하고 바인딩하는 데 <xref:System.Windows.Data.Binding.XPath%2A> 사용되는 식은 접두사를 포함하지 않아도 되므로 간단한 데이터 제도에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="25d8c-121">더 복잡한 데이터 제도는 데이터에 대한 여러 접두사를 정의하고 루트의 XML 네임스페이스에 대한 특정 접두사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="25d8c-122">이 경우 모든 <xref:System.Windows.Data.Binding.XPath%2A> 표현식 참조에는 적절한 네임스페이스 매핑접두사가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="25d8c-123">자세한 내용은 [데이터 바인딩 개요를](../data/data-binding-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="25d8c-123">For more information, see [Data Binding Overview](../data/data-binding-overview.md).</span></span>

<span data-ttu-id="25d8c-124">기술적으로, `x:XData` 형식의 <xref:System.Xml.Serialization.IXmlSerializable>모든 속성의 내용으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="25d8c-125">그러나, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 유일한 눈에 띄는 구현이다.</span><span class="sxs-lookup"><span data-stu-id="25d8c-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="25d8c-126">참조</span><span class="sxs-lookup"><span data-stu-id="25d8c-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="25d8c-127">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="25d8c-127">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="25d8c-128">Binding 태그 확장</span><span class="sxs-lookup"><span data-stu-id="25d8c-128">Binding Markup Extension</span></span>](../../framework/wpf/advanced/binding-markup-extension.md)
