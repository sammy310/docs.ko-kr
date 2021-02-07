---
description: '자세한 정보: XML 하위 항목 축 속성 (Visual Basic)'
title: XML Descendant Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Basic]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: c356d4d6f9a84755e9df171b26060fc6bfc4ead6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768781"
---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="8b5a4-103">XML 하위 항목 축 속성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b5a4-103">XML Descendant Axis Property (Visual Basic)</span></span>

<span data-ttu-id="8b5a4-104"><xref:System.Xml.Linq.XElement>개체, <xref:System.Xml.Linq.XDocument> 개체, 개체 컬렉션 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체 컬렉션의 하위 항목에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-104">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

## <a name="syntax"></a><span data-ttu-id="8b5a4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b5a4-105">Syntax</span></span>

```vb
object...<descendant>
```

## <a name="parts"></a><span data-ttu-id="8b5a4-106">부분</span><span class="sxs-lookup"><span data-stu-id="8b5a4-106">Parts</span></span>

<span data-ttu-id="8b5a4-107">`object` 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-107">`object` Required.</span></span> <span data-ttu-id="8b5a4-108"><xref:System.Xml.Linq.XElement> 개체, <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 개체의 컬렉션 또는 <xref:System.Xml.Linq.XDocument> 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-108">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

<span data-ttu-id="8b5a4-109">`...<` 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-109">`...<` Required.</span></span> <span data-ttu-id="8b5a4-110">하위 축 속성의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-110">Denotes the start of a descendant axis property.</span></span>

<span data-ttu-id="8b5a4-111">`descendant` 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-111">`descendant` Required.</span></span> <span data-ttu-id="8b5a4-112">[. 형식으로 액세스할 하위 노드의 이름입니다 `prefix:]name` .</span><span class="sxs-lookup"><span data-stu-id="8b5a4-112">Name of the descendant nodes to access, of the form [`prefix:]name`.</span></span>

|<span data-ttu-id="8b5a4-113">파트</span><span class="sxs-lookup"><span data-stu-id="8b5a4-113">Part</span></span>|<span data-ttu-id="8b5a4-114">설명</span><span class="sxs-lookup"><span data-stu-id="8b5a4-114">Description</span></span>|
|----------|-----------------|
|`prefix`|<span data-ttu-id="8b5a4-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-115">Optional.</span></span> <span data-ttu-id="8b5a4-116">하위 노드에 대 한 XML 네임 스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-116">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="8b5a4-117">는 문을 사용 하 여 정의 된 전역 XML 네임 스페이스 여야 합니다 `Imports` .</span><span class="sxs-lookup"><span data-stu-id="8b5a4-117">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|
|`name`|<span data-ttu-id="8b5a4-118">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-118">Required.</span></span> <span data-ttu-id="8b5a4-119">하위 노드의 로컬 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-119">Local name of the descendant node.</span></span> <span data-ttu-id="8b5a4-120">[선언 된 XML 요소 및 특성의 이름](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-120">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|

<span data-ttu-id="8b5a4-121">`>` 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-121">`>` Required.</span></span> <span data-ttu-id="8b5a4-122">하위 축 속성의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-122">Denotes the end of a descendant axis property.</span></span>

## <a name="return-value"></a><span data-ttu-id="8b5a4-123">Return Value</span><span class="sxs-lookup"><span data-stu-id="8b5a4-123">Return Value</span></span>

<span data-ttu-id="8b5a4-124"><xref:System.Xml.Linq.XElement> 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>

## <a name="remarks"></a><span data-ttu-id="8b5a4-125">설명</span><span class="sxs-lookup"><span data-stu-id="8b5a4-125">Remarks</span></span>

<span data-ttu-id="8b5a4-126">XML 하위 항목 축 속성을 사용 하 여 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체, 또는 개체의 컬렉션에서 이름별로 하위 노드에 액세스할 수 있습니다 <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> .</span><span class="sxs-lookup"><span data-stu-id="8b5a4-126">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="8b5a4-127">XML 속성을 사용 `Value` 하 여 반환 된 컬렉션에서 첫 번째 하위 노드의 값에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-127">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="8b5a4-128">자세한 내용은 [XML Value 속성](xml-value-property.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-128">For more information, see [XML Value Property](xml-value-property.md).</span></span>

<span data-ttu-id="8b5a4-129">Visual Basic 컴파일러는 하위 항목 축 속성을 메서드에 대 한 호출로 변환 합니다 <xref:System.Xml.Linq.XContainer.Descendants%2A> .</span><span class="sxs-lookup"><span data-stu-id="8b5a4-129">The Visual Basic compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="8b5a4-130">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="8b5a4-130">XML Namespaces</span></span>

<span data-ttu-id="8b5a4-131">하위 축 속성의 이름에는 문과 함께 전역적으로 선언 된 XML 네임 스페이스도 사용할 수 있습니다 `Imports` .</span><span class="sxs-lookup"><span data-stu-id="8b5a4-131">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="8b5a4-132">XML 요소 리터럴 내에서 로컬로 선언 된 XML 네임 스페이스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-132">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="8b5a4-133">자세한 내용은 [Imports 문 (XML 네임 스페이스)](../statements/imports-statement-xml-namespace.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-133">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>

## <a name="example"></a><span data-ttu-id="8b5a4-134">예제</span><span class="sxs-lookup"><span data-stu-id="8b5a4-134">Example</span></span>

<span data-ttu-id="8b5a4-135">다음 예제에서는 라는 첫 번째 하위 노드의 값 `name` 과 개체에서 명명 된 모든 하위 노드의 값에 액세스 하는 방법을 보여 줍니다 `phone` `contacts` .</span><span class="sxs-lookup"><span data-stu-id="8b5a4-135">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

<span data-ttu-id="8b5a4-136">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-136">This code displays the following text:</span></span>

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a><span data-ttu-id="8b5a4-137">예제</span><span class="sxs-lookup"><span data-stu-id="8b5a4-137">Example</span></span>

<span data-ttu-id="8b5a4-138">다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="8b5a4-138">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="8b5a4-139">그런 다음 네임 스페이스의 접두사를 사용 하 여 XML 리터럴을 만들고 정규화 된 이름을 사용 하 여 첫 번째 자식 노드의 값에 액세스 합니다 `ns:name` .</span><span class="sxs-lookup"><span data-stu-id="8b5a4-139">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

<span data-ttu-id="8b5a4-140">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5a4-140">This code displays the following text:</span></span>

`Name: Patrick Hines`

## <a name="see-also"></a><span data-ttu-id="8b5a4-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b5a4-141">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="8b5a4-142">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="8b5a4-142">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="8b5a4-143">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="8b5a4-143">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="8b5a4-144">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="8b5a4-144">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="8b5a4-145">선언된 XML 요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="8b5a4-145">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
