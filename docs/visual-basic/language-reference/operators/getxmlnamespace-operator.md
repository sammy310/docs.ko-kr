---
description: '자세한 정보: GetXmlNamespace 연산자 (Visual Basic)'
title: GetXmlNamespace 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: 704ac22493a0d6ce1255d171ae3b418313b74f09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665915"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="a4d7c-103">GetXmlNamespace 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4d7c-103">GetXmlNamespace Operator (Visual Basic)</span></span>

<span data-ttu-id="a4d7c-104">지정 된 <xref:System.Xml.Linq.XNamespace> XML 네임 스페이스 접두사에 해당 하는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a4d7c-104">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4d7c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4d7c-105">Syntax</span></span>  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="a4d7c-106">부분</span><span class="sxs-lookup"><span data-stu-id="a4d7c-106">Parts</span></span>  

 `xmlNamespacePrefix`  
 <span data-ttu-id="a4d7c-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a4d7c-107">Optional.</span></span> <span data-ttu-id="a4d7c-108">XML 네임 스페이스 접두사를 식별 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a4d7c-108">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="a4d7c-109">제공 되는 경우이 문자열은 올바른 XML 식별자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4d7c-109">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="a4d7c-110">자세한 내용은 [선언 된 XML 요소 및 특성의 이름](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4d7c-110">For more information, see [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="a4d7c-111">접두사가 지정 되지 않은 경우에는 기본 네임 스페이스가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4d7c-111">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="a4d7c-112">기본 네임 스페이스를 지정 하지 않으면 빈 네임 스페이스가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4d7c-112">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4d7c-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="a4d7c-113">Return Value</span></span>  

 <span data-ttu-id="a4d7c-114"><xref:System.Xml.Linq.XNamespace>XML 네임 스페이스 접두사에 해당 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a4d7c-114">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4d7c-115">설명</span><span class="sxs-lookup"><span data-stu-id="a4d7c-115">Remarks</span></span>  

 <span data-ttu-id="a4d7c-116">`GetXmlNamespace`연산자는 <xref:System.Xml.Linq.XNamespace> XML 네임 스페이스 접두사에 해당 하는 개체를 가져옵니다 `xmlNamespacePrefix` .</span><span class="sxs-lookup"><span data-stu-id="a4d7c-116">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="a4d7c-117">Xml 리터럴 및 XML 축 속성에 XML 네임 스페이스 접두사를 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4d7c-117">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="a4d7c-118">그러나 `GetXmlNamespace` <xref:System.Xml.Linq.XNamespace> 코드에서 사용할 수 있으려면 먼저 연산자를 사용 하 여 네임 스페이스 접두사를 개체로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4d7c-118">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="a4d7c-119">정규화 되지 않은 요소 이름을 개체에 추가 <xref:System.Xml.Linq.XNamespace> 하 여 <xref:System.Xml.Linq.XName> 많은 메서드에 필요한 정규화 된 개체를 가져올 수 있습니다 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a4d7c-119">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4d7c-120">예제</span><span class="sxs-lookup"><span data-stu-id="a4d7c-120">Example</span></span>  

 <span data-ttu-id="a4d7c-121">다음 예제에서는 `ns` XML 네임 스페이스 접두사로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a4d7c-121">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="a4d7c-122">그런 다음 네임 스페이스의 접두사를 사용 하 여 XML 리터럴을 만들고 정규화 된 이름을 가진 첫 번째 자식 노드에 액세스 합니다 `ns:phone` .</span><span class="sxs-lookup"><span data-stu-id="a4d7c-122">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="a4d7c-123">그런 다음 해당 자식 노드를 서브루틴에 전달 `ShowName` 합니다 .이 서브루틴은 연산자를 사용 하 여 정규화 된 이름을 생성 합니다 `GetXmlNamespace` .</span><span class="sxs-lookup"><span data-stu-id="a4d7c-123">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="a4d7c-124">`ShowName`그러면 서브루틴이 정규화 된 이름을 메서드에 전달 하 여 <xref:System.Xml.Linq.XNode.Ancestors%2A> 부모 노드를 가져옵니다 `ns:contact` .</span><span class="sxs-lookup"><span data-stu-id="a4d7c-124">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 <span data-ttu-id="a4d7c-125">를 호출 하면 `TestGetXmlNamespace.RunSample()` 다음 텍스트를 포함 하는 메시지 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4d7c-125">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="a4d7c-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4d7c-126">See also</span></span>

- [<span data-ttu-id="a4d7c-127">Imports 문(XML 네임스페이스)</span><span class="sxs-lookup"><span data-stu-id="a4d7c-127">Imports Statement (XML Namespace)</span></span>](../statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="a4d7c-128">Visual Basic에서 XML에 액세스</span><span class="sxs-lookup"><span data-stu-id="a4d7c-128">Accessing XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/accessing-xml.md)
