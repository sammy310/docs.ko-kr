---
title: XML 자식 축 속성(Visual Basic)
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
ms.openlocfilehash: 88d0b1f315bc1bb9dc474604d222a8ebcc1e40aa
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582235"
---
# <a name="xml-child-axis-property-visual-basic"></a><span data-ttu-id="34733-102">XML 자식 축 속성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="34733-102">XML Child Axis Property (Visual Basic)</span></span>
<span data-ttu-id="34733-103"><xref:System.Xml.Linq.XElement> 개체, <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 개체 컬렉션 또는 <xref:System.Xml.Linq.XDocument> 개체 컬렉션 중 하나의 자식에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="34733-103">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34733-104">구문</span><span class="sxs-lookup"><span data-stu-id="34733-104">Syntax</span></span>  
  
```vb  
object.<child>  
```  
  
## <a name="parts"></a><span data-ttu-id="34733-105">요소</span><span class="sxs-lookup"><span data-stu-id="34733-105">Parts</span></span>  
  
|<span data-ttu-id="34733-106">용어</span><span class="sxs-lookup"><span data-stu-id="34733-106">Term</span></span>|<span data-ttu-id="34733-107">정의</span><span class="sxs-lookup"><span data-stu-id="34733-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="34733-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="34733-108">Required.</span></span> <span data-ttu-id="34733-109"><xref:System.Xml.Linq.XElement> 개체, <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 개체의 컬렉션 또는 <xref:System.Xml.Linq.XDocument> 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="34733-109">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>|  
|<span data-ttu-id="34733-110">. <</span><span class="sxs-lookup"><span data-stu-id="34733-110">.<</span></span>|<span data-ttu-id="34733-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="34733-111">Required.</span></span> <span data-ttu-id="34733-112">자식 축 속성의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34733-112">Denotes the start of a child axis property.</span></span>|  
|`child`|<span data-ttu-id="34733-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="34733-113">Required.</span></span> <span data-ttu-id="34733-114">[@No__t_0 형식으로 액세스할 자식 노드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="34733-114">Name of the child nodes to access, of the form [`prefix:]name`.</span></span><br /><br /> <span data-ttu-id="34733-115">-    `Prefix`-선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="34733-115">-   `Prefix` - Optional.</span></span> <span data-ttu-id="34733-116">자식 노드에 대한 XML 네임스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="34733-116">XML namespace prefix for the child node.</span></span> <span data-ttu-id="34733-117">`Imports` 문으로 정의되는 전역 XML 네임스페이스여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34733-117">Must be a global XML namespace defined with an `Imports` statement.</span></span><br /><span data-ttu-id="34733-118">-    `Name`-필수 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="34733-118">-   `Name` - Required.</span></span> <span data-ttu-id="34733-119">로컬 자식 노드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="34733-119">Local child node name.</span></span> <span data-ttu-id="34733-120">[선언 된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="34733-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
|>|<span data-ttu-id="34733-121">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="34733-121">Required.</span></span> <span data-ttu-id="34733-122">자식 축 속성의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34733-122">Denotes the end of a child axis property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="34733-123">반환 값</span><span class="sxs-lookup"><span data-stu-id="34733-123">Return Value</span></span>  
 <span data-ttu-id="34733-124"><xref:System.Xml.Linq.XElement> 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="34733-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34733-125">주의</span><span class="sxs-lookup"><span data-stu-id="34733-125">Remarks</span></span>  
 <span data-ttu-id="34733-126">XML 자식 축 속성을 사용하여 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체 모음에서 이름을 기준으로 자식 노드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34733-126">You can use an XML child axis property to access child nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="34733-127">XML을 `Value` 속성을 사용하여 반환 모음에 있는 첫 번째 자식 노드의 값에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="34733-127">Use the XML `Value` property to access the value of the first child node in the returned collection.</span></span> <span data-ttu-id="34733-128">자세한 내용은 [XML Value 속성](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="34733-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="34733-129">Visual Basic 컴파일러는 자식 축 속성을 <xref:System.Xml.Linq.XContainer.Elements%2A> 메서드에 대 한 호출로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="34733-129">The Visual Basic compiler converts child axis properties to calls to the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="34733-130">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="34733-130">XML Namespaces</span></span>  
 <span data-ttu-id="34733-131">자식 축 속성의 이름은 `Imports` 문을 사용해 전역적으로 선언된 XML 네임스페이스 접두사만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34733-131">The name in a child axis property can use only XML namespace prefixes declared globally with the `Imports` statement.</span></span> <span data-ttu-id="34733-132">XML 요소 리터럴 내에서 로컬로 선언된 XML 네임스페이스 접두사를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34733-132">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="34733-133">자세한 내용은 [Imports 문 (XML 네임 스페이스)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="34733-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="34733-134">예제</span><span class="sxs-lookup"><span data-stu-id="34733-134">Example</span></span>  
 <span data-ttu-id="34733-135">다음 예제에서는 `contact` 개체에서 이름이 `phone`인 자식 노드에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="34733-135">The following example shows how to access the child nodes named `phone` from the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#17)]  
  
 <span data-ttu-id="34733-136">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34733-136">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="34733-137">예제</span><span class="sxs-lookup"><span data-stu-id="34733-137">Example</span></span>  
 <span data-ttu-id="34733-138">다음 예제에서는 `contacts` 개체의 `contact` 자식 축 속성에서 반환된 컬렉션에서 이름이 `phone`인 자식 노드에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="34733-138">The following example shows how to access the child nodes named `phone` from the collection returned by the `contact` child axis property of the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#18)]  
  
 <span data-ttu-id="34733-139">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34733-139">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="34733-140">예제</span><span class="sxs-lookup"><span data-stu-id="34733-140">Example</span></span>  
 <span data-ttu-id="34733-141">다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="34733-141">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="34733-142">네임스페이스의 접두사를 사용하여 XML 리터럴을 만들고 정규화된 이름 `ns:name`을 가진 첫 번째 자식 노드에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="34733-142">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 <span data-ttu-id="34733-143">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34733-143">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="34733-144">참조</span><span class="sxs-lookup"><span data-stu-id="34733-144">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="34733-145">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="34733-145">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="34733-146">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="34733-146">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="34733-147">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="34733-147">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="34733-148">선언된 XML 요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="34733-148">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
