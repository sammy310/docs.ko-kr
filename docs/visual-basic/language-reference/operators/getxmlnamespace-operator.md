---
title: GetXmlNamespace 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: 4d6e738f4e3a47d73e37c395dd74fe19e99d81bd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353188"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="277bd-102">GetXmlNamespace 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="277bd-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="277bd-103">지정 된 XML 네임 스페이스 접두사에 해당 하는 <xref:System.Xml.Linq.XNamespace> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="277bd-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="277bd-104">구문</span><span class="sxs-lookup"><span data-stu-id="277bd-104">Syntax</span></span>  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="277bd-105">요소</span><span class="sxs-lookup"><span data-stu-id="277bd-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="277bd-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="277bd-106">Optional.</span></span> <span data-ttu-id="277bd-107">XML 네임 스페이스 접두사를 식별 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="277bd-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="277bd-108">제공 되는 경우이 문자열은 올바른 XML 식별자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="277bd-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="277bd-109">자세한 내용은 [선언 된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="277bd-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="277bd-110">접두사가 지정 되지 않은 경우에는 기본 네임 스페이스가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="277bd-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="277bd-111">기본 네임 스페이스를 지정 하지 않으면 빈 네임 스페이스가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="277bd-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="277bd-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="277bd-112">Return Value</span></span>  
 <span data-ttu-id="277bd-113">XML 네임 스페이스 접두사에 해당 하는 <xref:System.Xml.Linq.XNamespace> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="277bd-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="277bd-114">설명</span><span class="sxs-lookup"><span data-stu-id="277bd-114">Remarks</span></span>  
 <span data-ttu-id="277bd-115">`GetXmlNamespace` 연산자는 XML 네임 스페이스 접두사 `xmlNamespacePrefix`에 해당 하는 <xref:System.Xml.Linq.XNamespace> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="277bd-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="277bd-116">Xml 리터럴 및 XML 축 속성에 XML 네임 스페이스 접두사를 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="277bd-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="277bd-117">그러나 코드에서 사용할 수 있으려면 먼저 `GetXmlNamespace` 연산자를 사용 하 여 네임 스페이스 접두사를 <xref:System.Xml.Linq.XNamespace> 개체로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="277bd-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="277bd-118">정규화 되지 않은 요소 이름을 <xref:System.Xml.Linq.XNamespace> 개체에 추가 하 여 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 메서드가 필요로 하는 정규화 된 <xref:System.Xml.Linq.XName> 개체를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="277bd-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="277bd-119">예제</span><span class="sxs-lookup"><span data-stu-id="277bd-119">Example</span></span>  
 <span data-ttu-id="277bd-120">다음 예에서는 `ns` XML 네임 스페이스 접두사로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="277bd-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="277bd-121">그런 다음 네임 스페이스의 접두사를 사용 하 여 XML 리터럴을 만들고 `ns:phone`정규화 된 이름을 가진 첫 번째 자식 노드에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="277bd-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="277bd-122">그런 다음 해당 자식 노드를 `ShowName` 서브루틴에 전달 합니다. 그러면 `GetXmlNamespace` 연산자를 사용 하 여 정규화 된 이름을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="277bd-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="277bd-123">그러면 `ShowName` 서브루틴이 정규화 된 이름을 <xref:System.Xml.Linq.XNode.Ancestors%2A> 메서드로 전달 하 여 부모 `ns:contact` 노드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="277bd-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 <span data-ttu-id="277bd-124">`TestGetXmlNamespace.RunSample()`를 호출 하면 다음 텍스트를 포함 하는 메시지 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="277bd-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="277bd-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="277bd-125">See also</span></span>

- [<span data-ttu-id="277bd-126">Imports 문(XML 네임스페이스)</span><span class="sxs-lookup"><span data-stu-id="277bd-126">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="277bd-127">Visual Basic에서 XML에 액세스</span><span class="sxs-lookup"><span data-stu-id="277bd-127">Accessing XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
