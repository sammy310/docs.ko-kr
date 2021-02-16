---
description: 자세히 알아보기:의 LINQ to XML 개요 Visual Basic
title: LINQ to XML 개요
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: e70998706f62076a2528ac646df29e0c7081cb3d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480221"
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a><span data-ttu-id="e5934-103">Visual Basic의 LINQ to XML 개요</span><span class="sxs-lookup"><span data-stu-id="e5934-103">Overview of LINQ to XML in Visual Basic</span></span>

<span data-ttu-id="e5934-104">Visual Basic는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] xml 리터럴 및 xml 축 속성을 통해에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-104">Visual Basic provides support for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] through XML literals and XML axis properties.</span></span> <span data-ttu-id="e5934-105">이렇게 하면 Visual Basic 코드에서 XML로 작업 하는 데 친숙 하 고 편리한 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-105">This enables you to use a familiar, convenient syntax for working with XML in your Visual Basic code.</span></span> <span data-ttu-id="e5934-106">*Xml 리터럴을* 사용 하면 코드에 xml을 직접 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-106">*XML literals* enable you to include XML directly in your code.</span></span> <span data-ttu-id="e5934-107">*Xml 축 속성* 을 사용 하면 자식 노드, 하위 노드 및 xml 리터럴의 특성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-107">*XML axis properties* enable you to access child nodes, descendant nodes, and attributes of an XML literal.</span></span> <span data-ttu-id="e5934-108">자세한 내용은 [Xml 리터럴 개요](xml-literals-overview.md) 및 [Visual Basic의 xml 액세스](accessing-xml.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5934-108">For more information, see [XML Literals Overview](xml-literals-overview.md) and [Accessing XML in Visual Basic](accessing-xml.md).</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="e5934-109">는 LINQ (Language-Integrated 쿼리)를 활용 하기 위해 특별히 설계 된 메모리 내 XML 프로그래밍 API입니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-109">is an in-memory XML programming API designed specifically to take advantage of Language-Integrated Query (LINQ).</span></span> <span data-ttu-id="e5934-110">LINQ Api를 직접 호출할 수 있지만 Visual Basic만 XML 리터럴을 선언 하 고 XML 축 속성에 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-110">Although you can call the LINQ APIs directly, only Visual Basic enables you to declare XML literals and directly access XML axis properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5934-111">XML 리터럴 및 XML 축 속성은 ASP.NET 페이지의 선언적 코드에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-111">XML literals and XML axis properties are not supported in declarative code in an ASP.NET page.</span></span> <span data-ttu-id="e5934-112">Visual Basic XML 기능을 사용 하려면 코드를 ASP.NET 응용 프로그램의 코드를 사용 하는 페이지에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-112">To use Visual Basic XML features, put your code in a code-behind page in your ASP.NET application.</span></span>  
  
 <span data-ttu-id="e5934-113">[재생 단추](./media/overview-of-linq-to-xml/play-video-icon-example.gif) 관련 비디오 데모를 보려면 [LINQ to XML를 시작 하는 방법](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml) 및 [LINQ to XML를 사용 하 여 Excel 스프레드시트를 만드는 방법](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e5934-113">[Play button](./media/overview-of-linq-to-xml/play-video-icon-example.gif) For related video demonstrations, see [How Do I Get Started with LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml) and [How Do I Create Excel Spreadsheets using LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml).</span></span>
  
## <a name="creating-xml"></a><span data-ttu-id="e5934-114">XML 만들기</span><span class="sxs-lookup"><span data-stu-id="e5934-114">Creating XML</span></span>  

 <span data-ttu-id="e5934-115">Visual Basic에서 XML 트리를 만드는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-115">There are two ways to create XML trees in Visual Basic.</span></span> <span data-ttu-id="e5934-116">코드에서 직접 XML 리터럴을 선언 하거나 LINQ Api를 사용 하 여 트리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-116">You can declare an XML literal directly in code, or you can use the LINQ APIs to create the tree.</span></span> <span data-ttu-id="e5934-117">두 프로세스 모두 코드에서 XML 트리의 최종 구조를 반영할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-117">Both processes enable the code to reflect the final structure of the XML tree.</span></span> <span data-ttu-id="e5934-118">예를 들어 다음 코드 예제에서는 XML 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-118">For example, the following code example creates an XML element:</span></span>  
  
 [!code-vb[VbXmlSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 <span data-ttu-id="e5934-119">자세한 내용은 [Visual Basic에서 XML 만들기](creating-xml.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5934-119">For more information, see [Creating XML in Visual Basic](creating-xml.md).</span></span>  
  
## <a name="accessing-and-navigating-xml"></a><span data-ttu-id="e5934-120">XML 액세스 및 탐색</span><span class="sxs-lookup"><span data-stu-id="e5934-120">Accessing and Navigating XML</span></span>  

 <span data-ttu-id="e5934-121">Visual Basic XML 구조에 액세스 하 고 탐색 하기 위한 XML 축 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-121">Visual Basic provides XML axis properties for accessing and navigating XML structures.</span></span> <span data-ttu-id="e5934-122">이러한 속성을 사용 하면 XML 자식 요소 이름을 지정 하 여 XML 요소와 특성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-122">These properties enable you to access XML elements and attributes by specifying the XML child element names.</span></span> <span data-ttu-id="e5934-123">또는 요소와 특성을 탐색 하 고 찾기 위한 LINQ 메서드를 명시적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-123">Alternatively, you can explicitly call the LINQ methods for navigating and locating elements and attributes.</span></span> <span data-ttu-id="e5934-124">예를 들어 다음 코드 예제에서는 xml 축 속성을 사용 하 여 XML 요소의 특성 및 자식 요소를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-124">For example, the following code example uses XML axis properties to refer to the attributes and child elements of an XML element.</span></span> <span data-ttu-id="e5934-125">이 코드 예제에서는 LINQ 쿼리를 사용 하 여 자식 요소를 검색 하 고 XML 요소로 출력 하 여 변환을 효과적으로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-125">The code example uses a LINQ query to retrieve child elements and output them as XML elements, effectively performing a transform.</span></span>  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 <span data-ttu-id="e5934-126">자세한 내용은 [Visual Basic에서 XML 액세스](accessing-xml.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5934-126">For more information, see [Accessing XML in Visual Basic](accessing-xml.md).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="e5934-127">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="e5934-127">XML Namespaces</span></span>  

 <span data-ttu-id="e5934-128">Visual Basic를 사용 하면 문을 사용 하 여 전역 XML 네임 스페이스에 대 한 별칭을 지정할 수 있습니다 `Imports` .</span><span class="sxs-lookup"><span data-stu-id="e5934-128">Visual Basic enables you to specify an alias to a global XML namespace by using the `Imports` statement.</span></span> <span data-ttu-id="e5934-129">다음 예에서는 문을 사용 하 여 `Imports` XML 네임 스페이스를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-129">The following example shows how to use the `Imports` statement to import an XML namespace:</span></span>  
  
 [!code-vb[VbXMLSamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#1)]  
  
 <span data-ttu-id="e5934-130">Xml 축 속성에 액세스 하 고 xml 문서 및 요소에 대 한 XML 리터럴을 선언할 때 XML 네임 스페이스 별칭을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-130">You can use an XML namespace alias when you access XML axis properties and declare XML literals for XML documents and elements.</span></span>  
  
 <span data-ttu-id="e5934-131"><xref:System.Xml.Linq.XNamespace> [GetXmlNamespace 연산자](../../../language-reference/operators/getxmlnamespace-operator.md)를 사용 하 여 특정 네임 스페이스 접두사에 대 한 개체를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-131">You can retrieve an <xref:System.Xml.Linq.XNamespace> object for a particular namespace prefix by using the [GetXmlNamespace Operator](../../../language-reference/operators/getxmlnamespace-operator.md).</span></span>  
  
 <span data-ttu-id="e5934-132">자세한 내용은 [Imports 문 (XML 네임 스페이스)](../../../language-reference/statements/imports-statement-xml-namespace.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5934-132">For more information, see [Imports Statement (XML Namespace)](../../../language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
### <a name="using-xml-namespaces-in-xml-literals"></a><span data-ttu-id="e5934-133">XML 리터럴에서 XML 네임 스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="e5934-133">Using XML Namespaces in XML Literals</span></span>  

 <span data-ttu-id="e5934-134">다음 예제에서는 <xref:System.Xml.Linq.XElement> 전역 네임 스페이스를 사용 하는 개체를 만드는 방법을 보여 줍니다 `ns` .</span><span class="sxs-lookup"><span data-stu-id="e5934-134">The following example shows how to create an <xref:System.Xml.Linq.XElement> object that uses the global namespace `ns`:</span></span>  
  
 [!code-vb[VbXMLSamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#2)]  
  
 <span data-ttu-id="e5934-135">Visual Basic 컴파일러는 xml 네임 스페이스 별칭을 포함 하는 XML 리터럴을 특성과 함께 xml 네임 스페이스를 사용 하는 xml 표기법을 사용 하는 동등한 코드로 변환 합니다 `xmlns` .</span><span class="sxs-lookup"><span data-stu-id="e5934-135">The Visual Basic compiler translates XML literals that contain XML namespace aliases into equivalent code that uses the XML notation for using XML namespaces, with the `xmlns` attribute.</span></span> <span data-ttu-id="e5934-136">이전 섹션 예제의 코드는 컴파일될 때 다음 예제와 같이 기본적으로 동일한 실행 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-136">When compiled, the code in the previous section's example produces essentially the same executable code as the following example:</span></span>  
  
 [!code-vb[VbXMLSamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#3)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a><span data-ttu-id="e5934-137">XML 축 속성에 XML 네임 스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="e5934-137">Using XML Namespaces in XML Axis Properties</span></span>  

 <span data-ttu-id="e5934-138">Xml 리터럴에 선언 된 xml 네임 스페이스는 XML 축 속성에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-138">XML namespaces declared in XML literals are not available for use in XML axis properties.</span></span> <span data-ttu-id="e5934-139">그러나 전역 네임 스페이스는 XML 축 속성과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-139">However, global namespaces can be used with the XML axis properties.</span></span> <span data-ttu-id="e5934-140">콜론을 사용 하 여 로컬 요소 이름과 XML 네임 스페이스 접두사를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-140">Use a colon to separate the XML namespace prefix from the local element name.</span></span> <span data-ttu-id="e5934-141">다음은 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="e5934-141">Following is an example:</span></span>  
  
 [!code-vb[VbXMLSamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="e5934-142">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e5934-142">See also</span></span>

- [<span data-ttu-id="e5934-143">XML</span><span class="sxs-lookup"><span data-stu-id="e5934-143">XML</span></span>](index.md)
- [<span data-ttu-id="e5934-144">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="e5934-144">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="e5934-145">Visual Basic에서 XML에 액세스</span><span class="sxs-lookup"><span data-stu-id="e5934-145">Accessing XML in Visual Basic</span></span>](accessing-xml.md)
- [<span data-ttu-id="e5934-146">Visual Basic에서 XML 조작</span><span class="sxs-lookup"><span data-stu-id="e5934-146">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)
