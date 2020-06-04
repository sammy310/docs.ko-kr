---
title: XML Attribute Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
ms.openlocfilehash: 3f60190a949856cb2bbc2eba09d097c09089bea7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408434"
---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="f06ab-102">XML 특성 축 속성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f06ab-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="f06ab-103">개체의 특성 값 <xref:System.Xml.Linq.XElement> 또는 개체 컬렉션의 첫 번째 요소에 대 한 액세스를 제공 합니다 <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="f06ab-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f06ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="f06ab-104">Syntax</span></span>  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="f06ab-105">부분</span><span class="sxs-lookup"><span data-stu-id="f06ab-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="f06ab-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="f06ab-106">Required.</span></span> <span data-ttu-id="f06ab-107"><xref:System.Xml.Linq.XElement>개체 또는 개체의 컬렉션 <xref:System.Xml.Linq.XElement> 입니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="f06ab-108">.@</span><span class="sxs-lookup"><span data-stu-id="f06ab-108">.@</span></span>  
 <span data-ttu-id="f06ab-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="f06ab-109">Required.</span></span> <span data-ttu-id="f06ab-110">특성 축 속성의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="f06ab-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-111">Optional.</span></span> <span data-ttu-id="f06ab-112">가 Visual Basic의 올바른 식별자가 아닌 경우 특성 이름의 시작을 나타냅니다 `attribute` .</span><span class="sxs-lookup"><span data-stu-id="f06ab-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
 `attribute`  
 <span data-ttu-id="f06ab-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="f06ab-113">Required.</span></span> <span data-ttu-id="f06ab-114">[:] 형식의 액세스할 특성의 이름입니다 `prefix` `name` .</span><span class="sxs-lookup"><span data-stu-id="f06ab-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="f06ab-115">부분</span><span class="sxs-lookup"><span data-stu-id="f06ab-115">Part</span></span>|<span data-ttu-id="f06ab-116">Description</span><span class="sxs-lookup"><span data-stu-id="f06ab-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="f06ab-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-117">Optional.</span></span> <span data-ttu-id="f06ab-118">특성에 대 한 XML 네임 스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="f06ab-119">`Imports` 문으로 정의되는 전역 XML 네임스페이스여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="f06ab-120">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="f06ab-120">Required.</span></span> <span data-ttu-id="f06ab-121">로컬 특성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-121">Local attribute name.</span></span> <span data-ttu-id="f06ab-122">[선언 된 XML 요소 및 특성의 이름](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f06ab-122">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="f06ab-123">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-123">Optional.</span></span> <span data-ttu-id="f06ab-124">가 Visual Basic의 올바른 식별자가 아닌 경우 특성 이름의 끝을 나타냅니다 `attribute` .</span><span class="sxs-lookup"><span data-stu-id="f06ab-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f06ab-125">반환 값</span><span class="sxs-lookup"><span data-stu-id="f06ab-125">Return Value</span></span>  
 <span data-ttu-id="f06ab-126">의 값을 포함 하는 문자열입니다 `attribute` .</span><span class="sxs-lookup"><span data-stu-id="f06ab-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="f06ab-127">특성 이름이 없으면 `Nothing` 이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f06ab-128">설명</span><span class="sxs-lookup"><span data-stu-id="f06ab-128">Remarks</span></span>  
 <span data-ttu-id="f06ab-129">XML 특성 축 속성을 사용 하 여 <xref:System.Xml.Linq.XElement> 개체 또는 개체 컬렉션의 첫 번째 요소에서 이름별로 특성 값에 액세스할 수 있습니다 <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="f06ab-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="f06ab-130">이름으로 특성 값을 검색 하거나, @ identifier 앞에 새 이름을 지정 하 여 요소에 새 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="f06ab-131">@ Identifier를 사용 하 여 XML 특성을 참조 하는 경우 특성 값이 문자열로 반환 되 고 속성을 명시적으로 지정할 필요가 없습니다 <xref:System.Xml.Linq.XAttribute.Value%2A> .</span><span class="sxs-lookup"><span data-stu-id="f06ab-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="f06ab-132">XML 특성에 대 한 명명 규칙은 Visual Basic 식별자에 대 한 명명 규칙과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-132">The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers.</span></span> <span data-ttu-id="f06ab-133">올바른 Visual Basic 식별자가 아닌 이름을 가진 XML 특성에 액세스 하려면 이름을 꺾쇠 괄호 ()로 묶습니다 \< and > .</span><span class="sxs-lookup"><span data-stu-id="f06ab-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="f06ab-134">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="f06ab-134">XML Namespaces</span></span>  
 <span data-ttu-id="f06ab-135">특성 축 속성의 이름에는 문을 사용 하 여 전역적으로 선언 된 XML 네임 스페이스 접두사만 사용할 수 있습니다 `Imports` .</span><span class="sxs-lookup"><span data-stu-id="f06ab-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="f06ab-136">XML 요소 리터럴 내에서 로컬로 선언된 XML 네임스페이스 접두사를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="f06ab-137">자세한 내용은 [Imports 문 (XML 네임 스페이스)](../statements/imports-statement-xml-namespace.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f06ab-137">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f06ab-138">예제</span><span class="sxs-lookup"><span data-stu-id="f06ab-138">Example</span></span>  
 <span data-ttu-id="f06ab-139">다음 예제에서는 `type` 라는 xml 요소의 컬렉션에서 라는 xml 특성의 값을 가져오는 방법을 보여 줍니다 `phone` .</span><span class="sxs-lookup"><span data-stu-id="f06ab-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 <span data-ttu-id="f06ab-140">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-140">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="f06ab-141">예제</span><span class="sxs-lookup"><span data-stu-id="f06ab-141">Example</span></span>  
 <span data-ttu-id="f06ab-142">다음 예에서는 xml 요소에 대 한 특성을 XML의 일부로 선언적으로 만들고 개체의 인스턴스에 특성을 추가 하 여 동적으로 만드는 방법을 보여 줍니다 <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="f06ab-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="f06ab-143">`type`특성이 선언적 `owner` 으로 만들어지고 특성이 동적으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 <span data-ttu-id="f06ab-144">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-144">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="f06ab-145">예제</span><span class="sxs-lookup"><span data-stu-id="f06ab-145">Example</span></span>  
 <span data-ttu-id="f06ab-146">다음 예에서는 꺾쇠 괄호 구문을 사용 하 여 `number-type` Visual Basic에서 유효한 식별자가 아닌 이라는 XML 특성의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.</span></span>  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 <span data-ttu-id="f06ab-147">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-147">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="f06ab-148">예제</span><span class="sxs-lookup"><span data-stu-id="f06ab-148">Example</span></span>  
 <span data-ttu-id="f06ab-149">다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="f06ab-149">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="f06ab-150">그런 다음 네임 스페이스의 접두사를 사용 하 여 XML 리터럴을 만들고 정규화 된 이름 ""을 사용 하 여 첫 번째 자식 노드에 액세스 `ns:name` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 <span data-ttu-id="f06ab-151">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ab-151">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="f06ab-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f06ab-152">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="f06ab-153">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="f06ab-153">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="f06ab-154">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="f06ab-154">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="f06ab-155">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="f06ab-155">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="f06ab-156">선언된 XML 요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="f06ab-156">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
