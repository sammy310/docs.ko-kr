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
ms.openlocfilehash: d78c2fd63192dc499b119e5b038b92555511a695
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544806"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="b2d2d-102">x:XData 내장 XAML 형식</span><span class="sxs-lookup"><span data-stu-id="b2d2d-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="b2d2d-103">XAML 프로덕션 내에서 XML 데이터 아일랜드를 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2d2d-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="b2d2d-104">내의 XML 요소는 `x:XData` 기본 xaml 네임 스페이스 또는 다른 xaml 네임 스페이스의 일부인 것 처럼 XAML 프로세서에서 처리 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2d2d-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="b2d2d-105">`x:XData` 올바른 형식의 모든 XML을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2d2d-105">`x:XData` can contain arbitrary well-formed XML.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="b2d2d-106">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="b2d2d-106">XAML Object Element Usage</span></span>

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a><span data-ttu-id="b2d2d-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="b2d2d-107">XAML Values</span></span>

|||
|-|-|
|`elementDataRoot`|<span data-ttu-id="b2d2d-108">포함 된 데이터 아일랜드의 단일 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b2d2d-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="b2d2d-109">대부분의 최종 소비자의 경우 단일 루트를 포함 하지 않는 XML은 잘못 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2d2d-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="b2d2d-110">특히 `x:XData` 데이터 바인딩에 xml 원본을 사용 하는 WPF 또는 다른 여러 기술에 대 한 xml 데이터 소스로 사용 하는 경우 단일 루트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d2d-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|
|`[elementData]`|<span data-ttu-id="b2d2d-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b2d2d-111">Optional.</span></span> <span data-ttu-id="b2d2d-112">XML 데이터를 나타내는 XML입니다.</span><span class="sxs-lookup"><span data-stu-id="b2d2d-112">XML that represents the XML data.</span></span> <span data-ttu-id="b2d2d-113">요소 수에 관계 없이 요소 데이터와 중첩 된 요소가 다른 요소에 포함 될 수 있습니다. 그러나 XML의 일반 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2d2d-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b2d2d-114">설명</span><span class="sxs-lookup"><span data-stu-id="b2d2d-114">Remarks</span></span>

<span data-ttu-id="b2d2d-115">개체 내의 XML 요소는 `x:XData` 데이터 내에 포함 된 XMLDOM의 모든 가능한 네임 스페이스와 접두사를 다시 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2d2d-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>

<span data-ttu-id="b2d2d-116">`x:XData`클래스를 통해 .NET Xaml 서비스에서 XML 데이터 및 내장 XAML 형식에 프로그래밍 방식으로 액세스할 수 있습니다 <xref:System.Windows.Markup.XData> .</span><span class="sxs-lookup"><span data-stu-id="b2d2d-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="b2d2d-117">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="b2d2d-117">WPF Usage Notes</span></span>

<span data-ttu-id="b2d2d-118">`x:XData`개체는 주로의 자식 개체 <xref:System.Windows.Data.XmlDataProvider> 또는 속성의 자식 개체로 사용 됩니다 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> (XAML에서이는 일반적으로 속성 요소 구문으로 표현 됨).</span><span class="sxs-lookup"><span data-stu-id="b2d2d-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>

<span data-ttu-id="b2d2d-119">데이터는 일반적으로 데이터 아일랜드 내의 기본 XML 네임 스페이스를 새 기본 XML 네임 스페이스 (빈 문자열로 설정)로 다시 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d2d-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="b2d2d-120">이는 <xref:System.Windows.Data.Binding.XPath%2A> 데이터를 참조 하 고 바인딩하는 데 사용 되는 식이 접두사의 포함을 방지할 수 있기 때문에 단순 데이터 아일랜드에 가장 간편 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d2d-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="b2d2d-121">더 복잡 한 데이터 아일랜드는 데이터에 대 한 여러 접두사를 정의 하 고 루트의 XML 네임 스페이스에 대 한 특정 접두사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2d2d-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="b2d2d-122">이 경우 모든 <xref:System.Windows.Data.Binding.XPath%2A> 식 참조는 적절 한 네임 스페이스 매핑 접두사를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d2d-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="b2d2d-123">자세한 내용은 [데이터 바인딩 개요](../data/data-binding-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2d2d-123">For more information, see [Data Binding Overview](../data/data-binding-overview.md).</span></span>

<span data-ttu-id="b2d2d-124">기술적으로 `x:XData` 는 형식의 모든 속성의 콘텐츠로 사용할 수 있습니다 <xref:System.Xml.Serialization.IXmlSerializable> .</span><span class="sxs-lookup"><span data-stu-id="b2d2d-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="b2d2d-125">그러나 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 는 유일한 중요 한 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="b2d2d-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2d2d-126">참조</span><span class="sxs-lookup"><span data-stu-id="b2d2d-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="b2d2d-127">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="b2d2d-127">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="b2d2d-128">바인딩 태그 확장</span><span class="sxs-lookup"><span data-stu-id="b2d2d-128">Binding Markup Extension</span></span>](/dotnet/desktop/wpf/advanced/binding-markup-extension)
