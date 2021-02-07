---
description: '자세히 알아보기: XML Value 속성 (Visual Basic)'
title: XML 값 속성
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 49762c1fcc0059472a5be11726aa344a001807ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768768"
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="97d52-103">XML Value 속성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97d52-103">XML Value Property (Visual Basic)</span></span>

<span data-ttu-id="97d52-104">개체 컬렉션의 첫 번째 요소 값에 대 한 액세스를 제공 <xref:System.Xml.Linq.XElement> 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d52-104">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>

## <a name="syntax"></a><span data-ttu-id="97d52-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="97d52-105">Syntax</span></span>

```vb
object.Value
```

## <a name="parts"></a><span data-ttu-id="97d52-106">부분</span><span class="sxs-lookup"><span data-stu-id="97d52-106">Parts</span></span>

|<span data-ttu-id="97d52-107">용어</span><span class="sxs-lookup"><span data-stu-id="97d52-107">Term</span></span>|<span data-ttu-id="97d52-108">정의</span><span class="sxs-lookup"><span data-stu-id="97d52-108">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="97d52-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="97d52-109">Required.</span></span> <span data-ttu-id="97d52-110"><xref:System.Xml.Linq.XElement> 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="97d52-110">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  

## <a name="return-value"></a><span data-ttu-id="97d52-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="97d52-111">Return Value</span></span>

 <span data-ttu-id="97d52-112">`String`컬렉션의 첫 번째 요소 값을 포함 하는 이거나, `Nothing` 컬렉션이 비어 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="97d52-112">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>

## <a name="remarks"></a><span data-ttu-id="97d52-113">설명</span><span class="sxs-lookup"><span data-stu-id="97d52-113">Remarks</span></span>

 <span data-ttu-id="97d52-114"><xref:System.Xml.Linq.XElement.Value%2A>속성을 사용 하면 개체 컬렉션의 첫 번째 요소 값에 쉽게 액세스할 수 <xref:System.Xml.Linq.XElement> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97d52-114">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="97d52-115">이 속성은 먼저 컬렉션에 하나 이상의 개체가 포함 되어 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d52-115">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="97d52-116">컬렉션이 비어 있으면이 속성은를 반환 `Nothing` 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d52-116">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="97d52-117">그렇지 않으면이 속성은 <xref:System.Xml.Linq.XElement.Value%2A> 컬렉션에 있는 첫 번째 요소의 속성 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d52-117">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>

> [!NOTE]
> <span data-ttu-id="97d52-118">' ' 식별자를 사용 하 여 XML 특성의 값에 액세스 하는 경우 \@ 특성 값이로 반환 되 `String` 고 속성을 명시적으로 지정할 필요가 없습니다 <xref:System.Xml.Linq.XAttribute.Value%2A> .</span><span class="sxs-lookup"><span data-stu-id="97d52-118">When you access the value of an XML attribute using the '\@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>

 <span data-ttu-id="97d52-119">컬렉션의 다른 요소에 액세스 하려면 XML 확장 인덱서 속성을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97d52-119">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="97d52-120">자세한 내용은 [확장 인덱서 속성](extension-indexer-property.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97d52-120">For more information, see [Extension Indexer Property](extension-indexer-property.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="97d52-121">상속</span><span class="sxs-lookup"><span data-stu-id="97d52-121">Inheritance</span></span>

 <span data-ttu-id="97d52-122">대부분의 사용자는를 구현할 필요가 없으므로 <xref:System.Collections.Generic.IEnumerable%601> 이 섹션을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97d52-122">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>

 <span data-ttu-id="97d52-123">속성은을 <xref:System.Xml.Linq.XElement.Value%2A> 구현 하는 형식에 대 한 확장 속성입니다 `IEnumerable(Of XElement)` .</span><span class="sxs-lookup"><span data-stu-id="97d52-123">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="97d52-124">이 확장 속성의 바인딩은 확장 메서드의 바인딩과 유사 합니다. 형식이 인터페이스 중 하나를 구현 하 고 이름이 "Value" 인 속성을 정의 하는 경우 해당 속성은 확장 속성 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d52-124">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="97d52-125">즉,을 <xref:System.Xml.Linq.XElement.Value%2A> 구현 하는 클래스에서 새 속성을 정의 하 여이 속성을 재정의할 수 있습니다 `IEnumerable(Of XElement)` .</span><span class="sxs-lookup"><span data-stu-id="97d52-125">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>

## <a name="example"></a><span data-ttu-id="97d52-126">예제</span><span class="sxs-lookup"><span data-stu-id="97d52-126">Example</span></span>

 <span data-ttu-id="97d52-127">다음 예제에서는 속성을 사용 하 여 <xref:System.Xml.Linq.XElement.Value%2A> 개체 컬렉션의 첫 번째 노드에 액세스 하는 방법을 보여 줍니다 <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="97d52-127">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="97d52-128">이 예제에서는 자식 축 속성을 사용 하 여 개체에 있는 라는 모든 자식 노드의 컬렉션을 가져옵니다 `phone` `contact` .</span><span class="sxs-lookup"><span data-stu-id="97d52-128">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>

 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]

 <span data-ttu-id="97d52-129">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="97d52-129">This code displays the following text:</span></span>

 `Phone number: 206-555-0144`

## <a name="example"></a><span data-ttu-id="97d52-130">예제</span><span class="sxs-lookup"><span data-stu-id="97d52-130">Example</span></span>

 <span data-ttu-id="97d52-131">다음 예제에서는 개체의 컬렉션에서 XML 특성의 값을 가져오는 방법을 보여 줍니다 <xref:System.Xml.Linq.XAttribute> .</span><span class="sxs-lookup"><span data-stu-id="97d52-131">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="97d52-132">이 예에서는 특성 축 속성을 사용 하 여 `type` 모든 요소에 대 한 특성 값을 표시 합니다 `phone` .</span><span class="sxs-lookup"><span data-stu-id="97d52-132">The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.</span></span>

 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]

 <span data-ttu-id="97d52-133">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="97d52-133">This code displays the following text:</span></span>

 ```console
 home
 work
```

## <a name="see-also"></a><span data-ttu-id="97d52-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97d52-134">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="97d52-135">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="97d52-135">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="97d52-136">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="97d52-136">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="97d52-137">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="97d52-137">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="97d52-138">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="97d52-138">Extension Methods</span></span>](../../programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="97d52-139">확장명 인덱서 속성</span><span class="sxs-lookup"><span data-stu-id="97d52-139">Extension Indexer Property</span></span>](extension-indexer-property.md)
- [<span data-ttu-id="97d52-140">XML Child Axis Property</span><span class="sxs-lookup"><span data-stu-id="97d52-140">XML Child Axis Property</span></span>](xml-child-axis-property.md)
- [<span data-ttu-id="97d52-141">XML Attribute Axis Property</span><span class="sxs-lookup"><span data-stu-id="97d52-141">XML Attribute Axis Property</span></span>](xml-attribute-axis-property.md)
