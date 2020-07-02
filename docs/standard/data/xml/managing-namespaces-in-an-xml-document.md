---
title: XML 문서의 네임스페이스 관리
description: XML 문서에서 네임스페이스를 관리하는 방법을 알아봅니다. XML 네임스페이스는 XML 문서의 요소 및 특성 이름을 사용자 지정 및 미리 정의된 URI와 연결합니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 682643fc-b848-4e42-8c0d-50deeaeb5f2a
ms.openlocfilehash: 3a3abd2e932b1afecab85e285b0e2c42eb1eb20f
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769264"
---
# <a name="managing-namespaces-in-an-xml-document"></a><span data-ttu-id="8b01f-104">XML 문서의 네임스페이스 관리</span><span class="sxs-lookup"><span data-stu-id="8b01f-104">Managing Namespaces in an XML Document</span></span>
<span data-ttu-id="8b01f-105">XML 네임스페이스는 XML 문서의 요소 및 특성 이름을 사용자 지정 및 미리 정의된 URI와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-105">XML namespaces associate element and attribute names in an XML document with custom and predefined URIs.</span></span> <span data-ttu-id="8b01f-106">이러한 연결을 만들려면 네임스페이스 URI의 접두사를 정의하고 해당 접두사를 사용하여 XML 데이터의 요소 및 특성 이름을 한정합니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-106">To create these associations, you define prefixes for namespace URIs, and use those prefixes to qualify element and attribute names in XML data.</span></span> <span data-ttu-id="8b01f-107">네임스페이스는 요소 및 특성 이름이 충돌하는 것을 막고 동일한 이름의 요소 및 특성이 처리 및 확인되도록 하는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-107">Namespaces prevent element and attribute name collisions, and enable elements and attributes of the same name to be handled and validated differently.</span></span>  
  
<a name="declare"></a>
## <a name="declaring-namespaces"></a><span data-ttu-id="8b01f-108">네임스페이스 선언</span><span class="sxs-lookup"><span data-stu-id="8b01f-108">Declaring namespaces</span></span>  
 <span data-ttu-id="8b01f-109">요소의 네임스페이스를 선언하려면 `xmlns:` 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-109">To declare a namespace on an element, you use the `xmlns:` attribute:</span></span>  
  
 `xmlns:<name>=<"uri">`  
  
 <span data-ttu-id="8b01f-110">`<name>`이 네임스페이스 접두사이고 `<"uri">`는 네임스페이스를 식별하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-110">where `<name>` is the namespace prefix and `<"uri">` is the URI that identifies the namespace.</span></span> <span data-ttu-id="8b01f-111">접두사를 선언한 후에는 접두사를 사용하여 XML 문서의 요소 및 특성을 한정하고 네임스페이스 URI와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-111">After you declare the prefix, you can use it to qualify elements and attributes in an XML document and associate them with the namespace URI.</span></span> <span data-ttu-id="8b01f-112">네임스페이스 접두사는 문서 전체에서 사용되므로 길이가 짧아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-112">Because the namespace prefix is used throughout a document, it should be short in length.</span></span>  
  
 <span data-ttu-id="8b01f-113">이 예제에서는 다음 두 개의 `BOOK` 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-113">This example defines two `BOOK` elements.</span></span> <span data-ttu-id="8b01f-114">첫 번째 요소는 접두사 `mybook`에 의해 한정되고 두 번째 요소는 접두사 `bb`에 의해 한정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-114">The first element is qualified by the prefix, `mybook`, and the second element is qualified by the prefix, `bb`.</span></span> <span data-ttu-id="8b01f-115">각 접두사는 다른 네임스페이스 URI와 연관되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-115">Each prefix is associated with a different namespace URI:</span></span>  
  
```xml  
<mybook:BOOK xmlns:mybook="http://www.contoso.com/books.dtd">  
<bb:BOOK xmlns:bb="urn:blueyonderairlines" />
</mybook>
```  
  
 <span data-ttu-id="8b01f-116">요소가 특정 네임스페이스의 일부임을 나타내기 위해 네임스페이스 접두사를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-116">To signify that an element is a part of a particular namespace, add the namespace prefix to it.</span></span> <span data-ttu-id="8b01f-117">예를 들어 `Author` 요소가 `mybook` 네임스페이스에 속하는 경우에는 `<mybook:Author>`로 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-117">For example, if a `Author` element belongs to the `mybook` namespace, it is declared as `<mybook:Author>`.</span></span>  
  
<a name="scope"></a>
## <a name="declaration-scope"></a><span data-ttu-id="8b01f-118">선언 범위</span><span class="sxs-lookup"><span data-stu-id="8b01f-118">Declaration scope</span></span>  
 <span data-ttu-id="8b01f-119">네임스페이스는 선언 지점부터 선언된 요소의 끝까지 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-119">A namespace is effective from its point of declaration until the end of the element it was declared in.</span></span> <span data-ttu-id="8b01f-120">이 예에서 `BOOK` 요소에서 정의된 네임스페이스는 `BOOK` 요소와 같은 `Publisher` 요소 외부의 요소에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-120">In this example, the namespace defined in the `BOOK` element doesn't apply to elements outside the `BOOK` element, such as the `Publisher` element:</span></span>  
  
```xml  
<Author>Joe Smith</Author>  
<BOOK xmlns:book="http://www.contoso.com">  
    <title>My Wonderful Day</title>  
      <price>$3.95</price>  
</BOOK>  
<Publisher>  
    <Name>MSPress</Name>  
</Publisher>  
```  
  
 <span data-ttu-id="8b01f-121">네임스페이스는 사용되기 전에 선언되어야 하지만 XML 문서의 맨 처음에 나타나야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-121">A namespace must be declared before it can be used, but it doesn't have to appear at the top of the XML document.</span></span>  
  
 <span data-ttu-id="8b01f-122">XML 문서에서 여러 네임스페이스를 사용하는 경우 네임스페이스 하나를 기본 네임스페이스로 정의하여 더 간결한 문서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-122">When you use multiple namespaces in an XML document, you can define one namespace as the default namespace to create a cleaner looking document.</span></span> <span data-ttu-id="8b01f-123">기본 네임스페이스는 루트 요소에서 정의되고 문서에서 정규화되지 않은 모든 요소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-123">The default namespace is declared in the root element and applies to all unqualified elements in the document.</span></span> <span data-ttu-id="8b01f-124">기본 네임스페이스는 요소에만 적용되고 특성에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-124">Default namespaces apply to elements only, not to attributes.</span></span>  
  
 <span data-ttu-id="8b01f-125">기본 네임스페이스를 사용하려면 요소의 선언에서 접두사와 콜론을 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-125">To use the default namespace, omit the prefix and the colon from the declaration on the element:</span></span>  
  
```xml  
<BOOK xmlns="http://www.contoso.com/books.dtd">  
...
</BOOK>
```  
  
## <a name="managing-namespaces"></a><span data-ttu-id="8b01f-126">네임스페이스 관리</span><span class="sxs-lookup"><span data-stu-id="8b01f-126">Managing namespaces</span></span>  
 <span data-ttu-id="8b01f-127"><xref:System.Xml.XmlNamespaceManager> 클래스는 네임스페이스 URI 및 해당 접두사의 컬렉션을 저장하고 이 컬렉션에서 네임스페이스를 조회, 추가 및 제거할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-127">The <xref:System.Xml.XmlNamespaceManager> class stores a collection of namespace URIs and their prefixes, and lets you look up, add, and remove namespaces from this collection.</span></span> <span data-ttu-id="8b01f-128">특정 컨텍스트에서 향상된 XML 처리 성능을 위해 이 클래스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-128">In certain contexts, this class is required for better XML processing performance.</span></span> <span data-ttu-id="8b01f-129">예를 들어, XPath 지원을 위해 <xref:System.Xml.Xsl.XsltContext> 클래스에서 <xref:System.Xml.XmlNamespaceManager>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-129">For example, the <xref:System.Xml.Xsl.XsltContext> class uses <xref:System.Xml.XmlNamespaceManager> for XPath support.</span></span>  
  
 <span data-ttu-id="8b01f-130">네임스페이스 관리자는 네임스페이스에 대한 유효성 검사를 수행하지 않지만 접두사 및 네임스페이스가 이미 확인되었고 [W3C 네임스페이스](https://www.w3.org/TR/REC-xml-names/) 사양을 따르는 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-130">The namespace manager doesn't perform any validation on the namespaces, but assumes that prefixes and namespaces have already been verified and conform to the [W3C Namespaces](https://www.w3.org/TR/REC-xml-names/) specification.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8b01f-131">[C#](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) 및 [Visual Basic](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)의 LINQ TO XML은 <xref:System.Xml.XmlNamespaceManager>를 사용하여 네임스페이스를 관리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-131">LINQ TO XML in [C#](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) and [Visual Basic](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md) don't use <xref:System.Xml.XmlNamespaceManager> to manage namespaces.</span></span> <span data-ttu-id="8b01f-132">LINQ to XML을 사용할 때 네임스페이스를 관리하는 방법에 대한 내용은 LINQ 설명서에서 [XML 네임스페이스 작업](../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md) 및 [XML 네임스페이스 작업(Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b01f-132">See [Working with XML Namespaces (C#)](../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md) and [Working with XML Namespaces (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md) in the LINQ documentation for information about managing namespaces when using LINQ to XML.</span></span>  
  
 <span data-ttu-id="8b01f-133">다음은 <xref:System.Xml.XmlNamespaceManager> 클래스로 수행할 수 있는 관리 및 조회 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="8b01f-133">Here are some of the management and lookup tasks you can perform with the <xref:System.Xml.XmlNamespaceManager> class.</span></span> <span data-ttu-id="8b01f-134">자세한 내용 및 예제는 각 메서드 또는 속성의 참조 페이지에 대한 링크를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b01f-134">For more information and examples, follow the links to the reference page for each method or property.</span></span>  
  
|<span data-ttu-id="8b01f-135">대상</span><span class="sxs-lookup"><span data-stu-id="8b01f-135">To</span></span>|<span data-ttu-id="8b01f-136">기능</span><span class="sxs-lookup"><span data-stu-id="8b01f-136">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="8b01f-137">네임스페이스 추가</span><span class="sxs-lookup"><span data-stu-id="8b01f-137">Add a namespace</span></span>|<span data-ttu-id="8b01f-138"><xref:System.Xml.XmlNamespaceManager.AddNamespace%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="8b01f-138"><xref:System.Xml.XmlNamespaceManager.AddNamespace%2A> method</span></span>|  
|<span data-ttu-id="8b01f-139">네임스페이스 제거</span><span class="sxs-lookup"><span data-stu-id="8b01f-139">Remove a namespace</span></span>|<span data-ttu-id="8b01f-140"><xref:System.Xml.XmlNamespaceManager.RemoveNamespace%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="8b01f-140"><xref:System.Xml.XmlNamespaceManager.RemoveNamespace%2A> method</span></span>|  
|<span data-ttu-id="8b01f-141">기본 네임스페이스에 대한 URI 찾기</span><span class="sxs-lookup"><span data-stu-id="8b01f-141">Find the URI for the default namespace</span></span>|<span data-ttu-id="8b01f-142"><xref:System.Xml.XmlNamespaceManager.DefaultNamespace%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="8b01f-142"><xref:System.Xml.XmlNamespaceManager.DefaultNamespace%2A> property</span></span>|  
|<span data-ttu-id="8b01f-143">네임스페이스 접두사에 대한 URI 찾기</span><span class="sxs-lookup"><span data-stu-id="8b01f-143">Find the URI for a namespace prefix</span></span>|<span data-ttu-id="8b01f-144"><xref:System.Xml.XmlNamespaceManager.LookupNamespace%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="8b01f-144"><xref:System.Xml.XmlNamespaceManager.LookupNamespace%2A> method</span></span>|  
|<span data-ttu-id="8b01f-145">네임스페이스 URI에 대한 접두사 찾기</span><span class="sxs-lookup"><span data-stu-id="8b01f-145">Find the prefix for a namespace URI</span></span>|<span data-ttu-id="8b01f-146"><xref:System.Xml.XmlNamespaceManager.LookupPrefix%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="8b01f-146"><xref:System.Xml.XmlNamespaceManager.LookupPrefix%2A> method</span></span>|  
|<span data-ttu-id="8b01f-147">현재 노드의 네임스페이스 목록 가져오기</span><span class="sxs-lookup"><span data-stu-id="8b01f-147">Get a list of namespaces in the current node</span></span>|<span data-ttu-id="8b01f-148"><xref:System.Xml.XmlNamespaceManager.GetNamespacesInScope%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="8b01f-148"><xref:System.Xml.XmlNamespaceManager.GetNamespacesInScope%2A> method</span></span>|  
|<span data-ttu-id="8b01f-149">네임스페이스 범위 지정</span><span class="sxs-lookup"><span data-stu-id="8b01f-149">Scope a namespace</span></span>|<span data-ttu-id="8b01f-150"><xref:System.Xml.XmlNamespaceManager.PushScope%2A> 및 <xref:System.Xml.XmlNamespaceManager.PopScope%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="8b01f-150"><xref:System.Xml.XmlNamespaceManager.PushScope%2A> and <xref:System.Xml.XmlNamespaceManager.PopScope%2A> methods</span></span>|  
|<span data-ttu-id="8b01f-151">접두사가 현재 범위에서 정의되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="8b01f-151">Check whether a prefix is defined in the current scope</span></span>|<span data-ttu-id="8b01f-152"><xref:System.Xml.XmlNamespaceManager.HasNamespace%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="8b01f-152"><xref:System.Xml.XmlNamespaceManager.HasNamespace%2A> method</span></span>|  
|<span data-ttu-id="8b01f-153">접두사와 URI를 찾는 데 사용된 이름 테이블 가져오기</span><span class="sxs-lookup"><span data-stu-id="8b01f-153">Get the name table used to look up prefixes and URIs</span></span>|<span data-ttu-id="8b01f-154"><xref:System.Xml.XmlNamespaceManager.NameTable%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="8b01f-154"><xref:System.Xml.XmlNamespaceManager.NameTable%2A> property</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b01f-155">참조</span><span class="sxs-lookup"><span data-stu-id="8b01f-155">See also</span></span>

- <xref:System.Xml.XmlNamespaceManager>
- [<span data-ttu-id="8b01f-156">XML 문서 및 데이터</span><span class="sxs-lookup"><span data-stu-id="8b01f-156">XML Documents and Data</span></span>](index.md)
