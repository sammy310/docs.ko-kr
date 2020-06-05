---
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
ms.openlocfilehash: 90dc22d12be5566fa1ee40f6b0e48eff8088e67b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400268"
---
# <a name="xml-child-axis-property-visual-basic"></a><span data-ttu-id="36bd5-102">XML 자식 축 속성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36bd5-102">XML Child Axis Property (Visual Basic)</span></span>
<span data-ttu-id="36bd5-103"><xref:System.Xml.Linq.XElement> 개체, <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 개체 컬렉션 또는 <xref:System.Xml.Linq.XDocument> 개체 컬렉션 중 하나의 자식에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-103">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36bd5-104">구문</span><span class="sxs-lookup"><span data-stu-id="36bd5-104">Syntax</span></span>  
  
```vb  
object.<child>  
```  
  
## <a name="parts"></a><span data-ttu-id="36bd5-105">부분</span><span class="sxs-lookup"><span data-stu-id="36bd5-105">Parts</span></span>  
  
|<span data-ttu-id="36bd5-106">용어</span><span class="sxs-lookup"><span data-stu-id="36bd5-106">Term</span></span>|<span data-ttu-id="36bd5-107">정의</span><span class="sxs-lookup"><span data-stu-id="36bd5-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="36bd5-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="36bd5-108">Required.</span></span> <span data-ttu-id="36bd5-109"><xref:System.Xml.Linq.XElement> 개체, <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 개체의 컬렉션 또는 <xref:System.Xml.Linq.XDocument> 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-109">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>|  
|<span data-ttu-id="36bd5-110">. <</span><span class="sxs-lookup"><span data-stu-id="36bd5-110">.<</span></span>|<span data-ttu-id="36bd5-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="36bd5-111">Required.</span></span> <span data-ttu-id="36bd5-112">자식 축 속성의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-112">Denotes the start of a child axis property.</span></span>|  
|`child`|<span data-ttu-id="36bd5-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="36bd5-113">Required.</span></span> <span data-ttu-id="36bd5-114">양식에 액세스할 자식 노드의 이름입니다 `[prefix:]name` .</span><span class="sxs-lookup"><span data-stu-id="36bd5-114">Name of the child nodes to access, of the form `[prefix:]name`.</span></span><br /><br /> <span data-ttu-id="36bd5-115">-   `Prefix`필드.</span><span class="sxs-lookup"><span data-stu-id="36bd5-115">-   `Prefix` - Optional.</span></span> <span data-ttu-id="36bd5-116">자식 노드에 대한 XML 네임스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-116">XML namespace prefix for the child node.</span></span> <span data-ttu-id="36bd5-117">`Imports` 문으로 정의되는 전역 XML 네임스페이스여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-117">Must be a global XML namespace defined with an `Imports` statement.</span></span><br /><span data-ttu-id="36bd5-118">-   `Name`하다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-118">-   `Name` - Required.</span></span> <span data-ttu-id="36bd5-119">로컬 자식 노드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-119">Local child node name.</span></span> <span data-ttu-id="36bd5-120">[선언 된 XML 요소 및 특성의 이름](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36bd5-120">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
|>|<span data-ttu-id="36bd5-121">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="36bd5-121">Required.</span></span> <span data-ttu-id="36bd5-122">자식 축 속성의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-122">Denotes the end of a child axis property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="36bd5-123">반환 값</span><span class="sxs-lookup"><span data-stu-id="36bd5-123">Return Value</span></span>  
 <span data-ttu-id="36bd5-124"><xref:System.Xml.Linq.XElement> 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36bd5-125">설명</span><span class="sxs-lookup"><span data-stu-id="36bd5-125">Remarks</span></span>  
 <span data-ttu-id="36bd5-126">XML 자식 축 속성을 사용하여 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체 모음에서 이름을 기준으로 자식 노드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-126">You can use an XML child axis property to access child nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="36bd5-127">XML을 `Value` 속성을 사용하여 반환 모음에 있는 첫 번째 자식 노드의 값에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-127">Use the XML `Value` property to access the value of the first child node in the returned collection.</span></span> <span data-ttu-id="36bd5-128">자세한 내용은 [XML Value 속성](xml-value-property.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36bd5-128">For more information, see [XML Value Property](xml-value-property.md).</span></span>  
  
 <span data-ttu-id="36bd5-129">Visual Basic 컴파일러는 자식 축 속성을 메서드 호출로 변환 합니다 <xref:System.Xml.Linq.XContainer.Elements%2A> .</span><span class="sxs-lookup"><span data-stu-id="36bd5-129">The Visual Basic compiler converts child axis properties to calls to the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="36bd5-130">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="36bd5-130">XML Namespaces</span></span>  
 <span data-ttu-id="36bd5-131">자식 축 속성의 이름은 `Imports` 문을 사용해 전역적으로 선언된 XML 네임스페이스 접두사만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-131">The name in a child axis property can use only XML namespace prefixes declared globally with the `Imports` statement.</span></span> <span data-ttu-id="36bd5-132">XML 요소 리터럴 내에서 로컬로 선언된 XML 네임스페이스 접두사를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-132">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="36bd5-133">자세한 내용은 [Imports 문 (XML 네임 스페이스)](../statements/imports-statement-xml-namespace.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36bd5-133">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="36bd5-134">예제</span><span class="sxs-lookup"><span data-stu-id="36bd5-134">Example</span></span>  
 <span data-ttu-id="36bd5-135">다음 예제에서는 `contact` 개체에서 이름이 `phone`인 자식 노드에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-135">The following example shows how to access the child nodes named `phone` from the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#17)]  
  
 <span data-ttu-id="36bd5-136">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-136">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="36bd5-137">예제</span><span class="sxs-lookup"><span data-stu-id="36bd5-137">Example</span></span>  
 <span data-ttu-id="36bd5-138">다음 예제에서는 `contacts` 개체의 `contact` 자식 축 속성에서 반환된 컬렉션에서 이름이 `phone`인 자식 노드에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-138">The following example shows how to access the child nodes named `phone` from the collection returned by the `contact` child axis property of the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#18)]  
  
 <span data-ttu-id="36bd5-139">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-139">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="36bd5-140">예제</span><span class="sxs-lookup"><span data-stu-id="36bd5-140">Example</span></span>  
 <span data-ttu-id="36bd5-141">다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="36bd5-141">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="36bd5-142">네임스페이스의 접두사를 사용하여 XML 리터럴을 만들고 정규화된 이름 `ns:name`을 가진 첫 번째 자식 노드에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-142">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 <span data-ttu-id="36bd5-143">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="36bd5-143">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="36bd5-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36bd5-144">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="36bd5-145">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="36bd5-145">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="36bd5-146">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="36bd5-146">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="36bd5-147">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="36bd5-147">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="36bd5-148">선언된 XML 요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="36bd5-148">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
