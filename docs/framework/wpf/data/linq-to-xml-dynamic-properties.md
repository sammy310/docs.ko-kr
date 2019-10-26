---
title: LINQ to XML 동적 속성 참조
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: ca3684716f9b562d0e6a006c26730a1d1a28f8b1
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921217"
---
# <a name="linq-to-xml-dynamic-properties"></a><span data-ttu-id="c43f5-102">LINQ to XML 동적 속성</span><span class="sxs-lookup"><span data-stu-id="c43f5-102">LINQ to XML dynamic properties</span></span>

<span data-ttu-id="c43f5-103">이 단원에서는 LINQ to XML의 동적 속성에 대한 참조 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c43f5-103">This section provides reference information about the dynamic properties in LINQ to XML.</span></span> <span data-ttu-id="c43f5-104">특히 이러한 속성은 <xref:System.Xml.Linq.XAttribute> 네임스페이스에 있는 <xref:System.Xml.Linq.XElement> 및 <xref:System.Xml.Linq> 클래스에서 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="c43f5-104">Specifically, these properties are exposed by the <xref:System.Xml.Linq.XAttribute> and <xref:System.Xml.Linq.XElement> classes, which are in the <xref:System.Xml.Linq> namespace.</span></span>

<span data-ttu-id="c43f5-105">[LINQ to XML을 사용한 WPF 데이터 바인딩 개요](wpf-data-binding-with-linq-to-xml-overview.md) 항목에서 설명한 대로 각 동적 속성은 동일한 클래스의 표준 공용 속성 또는 메서드와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="c43f5-105">As explained in the topic [Overview of WPF data binding with LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md), each of the dynamic properties is equivalent to a standard public property or method in the same class.</span></span> <span data-ttu-id="c43f5-106">이러한 표준 멤버는 대부분의 용도에 사용되어야 하며 동적 속성은 특히 LINQ to XML 데이터 바인딩 시나리오에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c43f5-106">These standard members should be used for most purposes; dynamic properties are provided specifically for LINQ to XML data binding scenarios.</span></span> <span data-ttu-id="c43f5-107">이러한 클래스의 표준 멤버에 대한 자세한 내용은 <xref:System.Xml.Linq.XAttribute> 및 <xref:System.Xml.Linq.XElement> 참조 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c43f5-107">For more information about the standard members of these classes, see the <xref:System.Xml.Linq.XAttribute> and <xref:System.Xml.Linq.XElement> reference topics.</span></span>

<span data-ttu-id="c43f5-108">이 단원의 동적 속성은 확인되는 값과 관련하여 다음 두 가지 범주로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="c43f5-108">With respect to their resolved values, the dynamic properties in this section fall into two categories:</span></span>

- <span data-ttu-id="c43f5-109">단일 값으로 확인되는 `Value` 및 <xref:System.Xml.Linq.XAttribute> 클래스의 <xref:System.Xml.Linq.XElement> 속성과 같은 간단한 속성</span><span class="sxs-lookup"><span data-stu-id="c43f5-109">Simple ones, such as the `Value` properties in the <xref:System.Xml.Linq.XAttribute> and <xref:System.Xml.Linq.XElement> classes, that resolve to a single value.</span></span>

- <span data-ttu-id="c43f5-110">인덱서 형식으로 해석되는 <xref:System.Xml.Linq.XElement>의 [Elements](elements-xelement-dynamic-property.md) 및 [Descendants](descendants-xelement-dynamic-property.md) 속성과 같은 인덱싱된 값 -</span><span class="sxs-lookup"><span data-stu-id="c43f5-110">Indexed values, such as the [Elements](elements-xelement-dynamic-property.md) and [Descendants](descendants-xelement-dynamic-property.md) properties of <xref:System.Xml.Linq.XElement>, that resolve into an indexer type.</span></span> <span data-ttu-id="c43f5-111">인덱서 형식을 원하는 값이나 컬렉션으로 확인하려면 확장된 이름 매개 변수가 인덱서 형식에 전달되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c43f5-111">For indexer types to be resolved to the desired value or collection, an expanded name parameter must be passed to them.</span></span>

<span data-ttu-id="c43f5-112"><xref:System.Collections.Generic.IEnumerable%601> 형식의 인덱싱된 값을 반환하는 모든 동적 속성은 지연된 실행을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c43f5-112">All the dynamic properties that return an indexed value of type <xref:System.Collections.Generic.IEnumerable%601> use deferred execution.</span></span> <span data-ttu-id="c43f5-113">지연된 실행에 대한 자세한 내용은 [LINQ 쿼리 소개(C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c43f5-113">For more information about deferred execution, see [Introduction to LINQ queries (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries).</span></span>

## <a name="reference"></a><span data-ttu-id="c43f5-114">참고</span><span class="sxs-lookup"><span data-stu-id="c43f5-114">Reference</span></span>

- <xref:System.Xml.Linq>
- <xref:System.Xml.Linq.XElement?displayProperty=fullName>
- <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>

## <a name="see-also"></a><span data-ttu-id="c43f5-115">참조</span><span class="sxs-lookup"><span data-stu-id="c43f5-115">See also</span></span>

- [<span data-ttu-id="c43f5-116">LINQ to XML로 WPF 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="c43f5-116">WPF data binding with LINQ to XML</span></span>](wpf-data-binding-with-linq-to-xml-overview.md)
- [<span data-ttu-id="c43f5-117">LINQ to XML로 WPF 데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="c43f5-117">WPF data binding with LINQ to XML overview</span></span>](wpf-data-binding-with-linq-to-xml-overview.md)
- [<span data-ttu-id="c43f5-118">LINQ 쿼리 소개(C#)</span><span class="sxs-lookup"><span data-stu-id="c43f5-118">Introduction to LINQ queries (C#)</span></span>](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)
