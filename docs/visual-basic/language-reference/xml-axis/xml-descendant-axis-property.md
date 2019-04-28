---
title: XML 하위 항목 축 속성(Visual Basic)
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
ms.openlocfilehash: bc1dff6dc3b580079087f370212b7d3acd30e4fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938673"
---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="6af69-102">XML 하위 항목 축 속성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6af69-102">XML Descendant Axis Property (Visual Basic)</span></span>

<span data-ttu-id="6af69-103">다음의 하위 항목에 액세스할 수:는 <xref:System.Xml.Linq.XElement> 개체를 <xref:System.Xml.Linq.XDocument> 개체의 컬렉션인 <xref:System.Xml.Linq.XElement> 개체나 컬렉션 <xref:System.Xml.Linq.XDocument> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

## <a name="syntax"></a><span data-ttu-id="6af69-104">구문</span><span class="sxs-lookup"><span data-stu-id="6af69-104">Syntax</span></span>

```
object...<descendant>
```

## <a name="parts"></a><span data-ttu-id="6af69-105">요소</span><span class="sxs-lookup"><span data-stu-id="6af69-105">Parts</span></span>

<span data-ttu-id="6af69-106">`object` 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-106">`object` Required.</span></span> <span data-ttu-id="6af69-107"><xref:System.Xml.Linq.XElement> 개체, <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 개체의 컬렉션 또는 <xref:System.Xml.Linq.XDocument> 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

<span data-ttu-id="6af69-108">`...<` 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-108">`...<` Required.</span></span> <span data-ttu-id="6af69-109">하위 축 속성의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-109">Denotes the start of a descendant axis property.</span></span>

<span data-ttu-id="6af69-110">`descendant` 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-110">`descendant` Required.</span></span> <span data-ttu-id="6af69-111">폼에 액세스 하려면 하위 노드의 이름을 [`prefix:]name`합니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-111">Name of the descendant nodes to access, of the form [`prefix:]name`.</span></span>

|<span data-ttu-id="6af69-112">파트</span><span class="sxs-lookup"><span data-stu-id="6af69-112">Part</span></span>|<span data-ttu-id="6af69-113">설명</span><span class="sxs-lookup"><span data-stu-id="6af69-113">Description</span></span>|
|----------|-----------------|
|`prefix`|<span data-ttu-id="6af69-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-114">Optional.</span></span> <span data-ttu-id="6af69-115">하위 노드에 대 한 XML 네임 스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-115">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="6af69-116">사용 하 여 정의 된 전역 XML 네임 스페이스 여야는 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-116">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|
|`name`|<span data-ttu-id="6af69-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="6af69-117">Required.</span></span> <span data-ttu-id="6af69-118">하위 노드의 로컬 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-118">Local name of the descendant node.</span></span> <span data-ttu-id="6af69-119">참조 [선언 된 XML 요소 및 특성의 이름을](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-119">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|

<span data-ttu-id="6af69-120">`>` 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-120">`>` Required.</span></span> <span data-ttu-id="6af69-121">하위 축 속성의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-121">Denotes the end of a descendant axis property.</span></span>

## <a name="return-value"></a><span data-ttu-id="6af69-122">반환 값</span><span class="sxs-lookup"><span data-stu-id="6af69-122">Return Value</span></span>

<span data-ttu-id="6af69-123"><xref:System.Xml.Linq.XElement> 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-123">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>

## <a name="remarks"></a><span data-ttu-id="6af69-124">설명</span><span class="sxs-lookup"><span data-stu-id="6af69-124">Remarks</span></span>

<span data-ttu-id="6af69-125">이름으로 하위 노드에 액세스 하는 XML 하위 축 속성을 사용할 수는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체 또는 컬렉션 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-125">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="6af69-126">XML을 사용 하 여 `Value` 반환된 된 컬렉션의 첫 번째 하위 노드의 값에 액세스 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-126">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="6af69-127">자세한 내용은 [XML 값 속성](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-127">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>

<span data-ttu-id="6af69-128">Visual Basic 컴파일러는 하위 항목 축 속성에 대 한 호출으로 변환 합니다는 <xref:System.Xml.Linq.XContainer.Descendants%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="6af69-128">The Visual Basic compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="6af69-129">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="6af69-129">XML Namespaces</span></span>

<span data-ttu-id="6af69-130">하위 축 속성의 이름을 사용 하 여 전역적으로 선언 된 XML 네임 스페이스만 사용할 수는 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-130">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="6af69-131">XML 요소 리터럴 내에서 로컬로 선언 된 XML 네임 스페이스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-131">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="6af69-132">자세한 내용은 [Imports 문 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-132">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>

## <a name="example"></a><span data-ttu-id="6af69-133">예제</span><span class="sxs-lookup"><span data-stu-id="6af69-133">Example</span></span>

<span data-ttu-id="6af69-134">다음 예제에서는 명명 된 첫 번째 하위 노드의 값에 액세스 하는 방법을 보여 줍니다 `name` 이라는 모든 하위 노드의 값 `phone` 에서 `contacts` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-134">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

<span data-ttu-id="6af69-135">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-135">This code displays the following text:</span></span>

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a><span data-ttu-id="6af69-136">예제</span><span class="sxs-lookup"><span data-stu-id="6af69-136">Example</span></span>

<span data-ttu-id="6af69-137">다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="6af69-137">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="6af69-138">다음 네임 스페이스의 접두사는 XML 리터럴을 만들고 정규화 된 이름 사용 하 여 첫 번째 자식 노드의 값에 액세스를 사용 하 여 `ns:name`입니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-138">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

<span data-ttu-id="6af69-139">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6af69-139">This code displays the following text:</span></span>

`Name: Patrick Hines`

## <a name="see-also"></a><span data-ttu-id="6af69-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="6af69-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="6af69-141">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="6af69-141">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="6af69-142">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="6af69-142">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="6af69-143">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="6af69-143">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="6af69-144">선언된 XML 요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="6af69-144">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
