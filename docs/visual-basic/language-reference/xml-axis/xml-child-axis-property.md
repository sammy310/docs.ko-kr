---
description: '자세한 정보: XML 자식 축 속성 (Visual Basic)'
title: XML Child Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyChildAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
ms.openlocfilehash: 54920ebd35635f215eb6cb58867be1e4a7acd847
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768794"
---
# <a name="xml-child-axis-property-visual-basic"></a><span data-ttu-id="6cae4-103">XML 자식 축 속성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6cae4-103">XML Child Axis Property (Visual Basic)</span></span>

<span data-ttu-id="6cae4-104"><xref:System.Xml.Linq.XElement> 개체, <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 개체 컬렉션 또는 <xref:System.Xml.Linq.XDocument> 개체 컬렉션 중 하나의 자식에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-104">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cae4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6cae4-105">Syntax</span></span>  
  
```vb  
object.<child>  
```  
  
## <a name="parts"></a><span data-ttu-id="6cae4-106">부분</span><span class="sxs-lookup"><span data-stu-id="6cae4-106">Parts</span></span>  
  
|<span data-ttu-id="6cae4-107">용어</span><span class="sxs-lookup"><span data-stu-id="6cae4-107">Term</span></span>|<span data-ttu-id="6cae4-108">정의</span><span class="sxs-lookup"><span data-stu-id="6cae4-108">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="6cae4-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="6cae4-109">Required.</span></span> <span data-ttu-id="6cae4-110"><xref:System.Xml.Linq.XElement> 개체, <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 개체의 컬렉션 또는 <xref:System.Xml.Linq.XDocument> 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-110">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>|  
|<span data-ttu-id="6cae4-111">. <</span><span class="sxs-lookup"><span data-stu-id="6cae4-111">.<</span></span>|<span data-ttu-id="6cae4-112">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-112">Required.</span></span> <span data-ttu-id="6cae4-113">자식 축 속성의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-113">Denotes the start of a child axis property.</span></span>|  
|`child`|<span data-ttu-id="6cae4-114">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-114">Required.</span></span> <span data-ttu-id="6cae4-115">양식에 액세스할 자식 노드의 이름입니다 `[prefix:]name` .</span><span class="sxs-lookup"><span data-stu-id="6cae4-115">Name of the child nodes to access, of the form `[prefix:]name`.</span></span><br /><br /> <span data-ttu-id="6cae4-116">-   `Prefix` 필드.</span><span class="sxs-lookup"><span data-stu-id="6cae4-116">-   `Prefix` - Optional.</span></span> <span data-ttu-id="6cae4-117">자식 노드에 대한 XML 네임스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-117">XML namespace prefix for the child node.</span></span> <span data-ttu-id="6cae4-118">`Imports` 문으로 정의되는 전역 XML 네임스페이스여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-118">Must be a global XML namespace defined with an `Imports` statement.</span></span><br /><span data-ttu-id="6cae4-119">-   `Name` 하다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-119">-   `Name` - Required.</span></span> <span data-ttu-id="6cae4-120">로컬 자식 노드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-120">Local child node name.</span></span> <span data-ttu-id="6cae4-121">[선언 된 XML 요소 및 특성의 이름](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6cae4-121">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
|>|<span data-ttu-id="6cae4-122">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-122">Required.</span></span> <span data-ttu-id="6cae4-123">자식 축 속성의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-123">Denotes the end of a child axis property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="6cae4-124">Return Value</span><span class="sxs-lookup"><span data-stu-id="6cae4-124">Return Value</span></span>  

 <span data-ttu-id="6cae4-125"><xref:System.Xml.Linq.XElement> 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-125">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6cae4-126">설명</span><span class="sxs-lookup"><span data-stu-id="6cae4-126">Remarks</span></span>  

 <span data-ttu-id="6cae4-127">XML 자식 축 속성을 사용하여 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체 모음에서 이름을 기준으로 자식 노드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-127">You can use an XML child axis property to access child nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="6cae4-128">XML을 `Value` 속성을 사용하여 반환 모음에 있는 첫 번째 자식 노드의 값에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-128">Use the XML `Value` property to access the value of the first child node in the returned collection.</span></span> <span data-ttu-id="6cae4-129">자세한 내용은 [XML Value 속성](xml-value-property.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6cae4-129">For more information, see [XML Value Property](xml-value-property.md).</span></span>  
  
 <span data-ttu-id="6cae4-130">Visual Basic 컴파일러는 자식 축 속성을 메서드 호출로 변환 합니다 <xref:System.Xml.Linq.XContainer.Elements%2A> .</span><span class="sxs-lookup"><span data-stu-id="6cae4-130">The Visual Basic compiler converts child axis properties to calls to the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="6cae4-131">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="6cae4-131">XML Namespaces</span></span>  

 <span data-ttu-id="6cae4-132">자식 축 속성의 이름은 `Imports` 문을 사용해 전역적으로 선언된 XML 네임스페이스 접두사만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-132">The name in a child axis property can use only XML namespace prefixes declared globally with the `Imports` statement.</span></span> <span data-ttu-id="6cae4-133">XML 요소 리터럴 내에서 로컬로 선언된 XML 네임스페이스 접두사를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-133">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="6cae4-134">자세한 내용은 [Imports 문 (XML 네임 스페이스)](../statements/imports-statement-xml-namespace.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6cae4-134">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cae4-135">예제</span><span class="sxs-lookup"><span data-stu-id="6cae4-135">Example</span></span>  

 <span data-ttu-id="6cae4-136">다음 예제에서는 `contact` 개체에서 이름이 `phone`인 자식 노드에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-136">The following example shows how to access the child nodes named `phone` from the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#17)]  
  
 <span data-ttu-id="6cae4-137">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-137">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="6cae4-138">예제</span><span class="sxs-lookup"><span data-stu-id="6cae4-138">Example</span></span>  

 <span data-ttu-id="6cae4-139">다음 예제에서는 `contacts` 개체의 `contact` 자식 축 속성에서 반환된 컬렉션에서 이름이 `phone`인 자식 노드에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-139">The following example shows how to access the child nodes named `phone` from the collection returned by the `contact` child axis property of the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#18)]  
  
 <span data-ttu-id="6cae4-140">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-140">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="6cae4-141">예제</span><span class="sxs-lookup"><span data-stu-id="6cae4-141">Example</span></span>  

 <span data-ttu-id="6cae4-142">다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="6cae4-142">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="6cae4-143">네임스페이스의 접두사를 사용하여 XML 리터럴을 만들고 정규화된 이름 `ns:name`을 가진 첫 번째 자식 노드에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-143">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 <span data-ttu-id="6cae4-144">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6cae4-144">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="6cae4-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6cae4-145">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="6cae4-146">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="6cae4-146">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="6cae4-147">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="6cae4-147">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="6cae4-148">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="6cae4-148">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="6cae4-149">선언된 XML 요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="6cae4-149">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
