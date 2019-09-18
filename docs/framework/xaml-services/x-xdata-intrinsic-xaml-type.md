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
ms.openlocfilehash: c5f729837b9bb52ca7d232ca66b58e283a2bcefc
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053706"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="ebf50-102">x:XData 내장 XAML 형식</span><span class="sxs-lookup"><span data-stu-id="ebf50-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="ebf50-103">XAML 프로덕션 내에서 XML 데이터 아일랜드를 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf50-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="ebf50-104">내의 `x:XData` XML 요소는 기본 xaml 네임 스페이스 또는 다른 xaml 네임 스페이스의 일부인 것 처럼 XAML 프로세서에서 처리 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebf50-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="ebf50-105">`x:XData`올바른 형식의 모든 XML을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf50-105">`x:XData` can contain arbitrary well-formed XML.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="ebf50-106">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="ebf50-106">XAML Object Element Usage</span></span>  
  
```xaml  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="ebf50-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="ebf50-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`elementDataRoot`|<span data-ttu-id="ebf50-108">포함된 데이터 아일랜드의 단일 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ebf50-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="ebf50-109">대부분의 최종 소비자의 경우 단일 루트를 포함 하지 않는 XML은 잘못 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebf50-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="ebf50-110">특히 데이터 바인딩에 xml 원본을 사용 하는 WPF 또는 `x:XData` 다른 여러 기술에 대 한 xml 데이터 소스로 사용 하는 경우 단일 루트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf50-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|  
|`[elementData]`|<span data-ttu-id="ebf50-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ebf50-111">Optional.</span></span> <span data-ttu-id="ebf50-112">XML 데이터를 나타내는 XML입니다.</span><span class="sxs-lookup"><span data-stu-id="ebf50-112">XML that represents the XML data.</span></span> <span data-ttu-id="ebf50-113">요소 수에 관계 없이 요소 데이터와 중첩 된 요소가 다른 요소에 포함 될 수 있습니다. 그러나 XML의 일반 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebf50-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebf50-114">설명</span><span class="sxs-lookup"><span data-stu-id="ebf50-114">Remarks</span></span>  
 <span data-ttu-id="ebf50-115">`x:XData` 개체 내의 XML 요소는 데이터 내에 포함 된 XMLDOM의 모든 가능한 네임 스페이스와 접두사를 다시 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf50-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>  
  
 <span data-ttu-id="ebf50-116">XML 데이터 및 `x:XData` 내장 xaml 형식에 대 한 프로그래밍 방식 액세스는 클래스를 <xref:System.Windows.Markup.XData> 통해 xaml 서비스 .NET Framework에서 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf50-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET Framework XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="ebf50-117">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="ebf50-117">WPF Usage Notes</span></span>  
 <span data-ttu-id="ebf50-118">개체 `x:XData` 는 주로 <xref:System.Windows.Data.XmlDataProvider>의 자식 개체 또는 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 속성의 자식 개체로 사용 됩니다 (XAML에서이는 일반적으로 속성 요소 구문으로 표현 됨).</span><span class="sxs-lookup"><span data-stu-id="ebf50-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>  
  
 <span data-ttu-id="ebf50-119">데이터는 일반적으로 데이터 아일랜드 내의 기본 XML 네임 스페이스를 새 기본 XML 네임 스페이스 (빈 문자열로 설정)로 다시 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf50-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="ebf50-120">이는 데이터를 참조 하 고 바인딩하는 <xref:System.Windows.Data.Binding.XPath%2A> 데 사용 되는 식이 접두사의 포함을 방지할 수 있기 때문에 단순 데이터 아일랜드에 가장 간편 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf50-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="ebf50-121">더 복잡 한 데이터 아일랜드는 데이터에 대 한 여러 접두사를 정의 하 고 루트의 XML 네임 스페이스에 대 한 특정 접두사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf50-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="ebf50-122">이 경우 모든 <xref:System.Windows.Data.Binding.XPath%2A> 식 참조는 적절 한 네임 스페이스 매핑 접두사를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf50-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="ebf50-123">자세한 내용은 [데이터 바인딩 개요](../wpf/data/data-binding-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ebf50-123">For more information, see [Data Binding Overview](../wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="ebf50-124">기술적으로는 형식의 <xref:System.Xml.Serialization.IXmlSerializable>모든 속성의 콘텐츠로 사용할 수있습니다.`x:XData`</span><span class="sxs-lookup"><span data-stu-id="ebf50-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="ebf50-125"><xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 그러나는 유일한 중요 한 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="ebf50-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebf50-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="ebf50-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="ebf50-127">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="ebf50-127">Data Binding Overview</span></span>](../wpf/data/data-binding-overview.md)
- [<span data-ttu-id="ebf50-128">Binding 태그 확장</span><span class="sxs-lookup"><span data-stu-id="ebf50-128">Binding Markup Extension</span></span>](../wpf/advanced/binding-markup-extension.md)
