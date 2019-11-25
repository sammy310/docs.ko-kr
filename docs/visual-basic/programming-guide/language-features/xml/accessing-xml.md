---
title: XML에 액세스
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 1fa1d94fc710272ac0ba9ea7167989da42a51fcd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351744"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="f2122-102">Visual Basic에서 XML에 액세스</span><span class="sxs-lookup"><span data-stu-id="f2122-102">Accessing XML in Visual Basic</span></span>
<span data-ttu-id="f2122-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span><span class="sxs-lookup"><span data-stu-id="f2122-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="f2122-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span><span class="sxs-lookup"><span data-stu-id="f2122-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="f2122-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f2122-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="f2122-106">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="f2122-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="f2122-107">Property description</span><span class="sxs-lookup"><span data-stu-id="f2122-107">Property description</span></span>|<span data-ttu-id="f2122-108">예제</span><span class="sxs-lookup"><span data-stu-id="f2122-108">Example</span></span>|<span data-ttu-id="f2122-109">설명</span><span class="sxs-lookup"><span data-stu-id="f2122-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="f2122-110">*child axis*</span><span class="sxs-lookup"><span data-stu-id="f2122-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="f2122-111">Gets all `phone` elements that are child elements of the `contact` element.</span><span class="sxs-lookup"><span data-stu-id="f2122-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="f2122-112">*attribute axis*</span><span class="sxs-lookup"><span data-stu-id="f2122-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="f2122-113">Gets all `type` attributes of the `phone` element.</span><span class="sxs-lookup"><span data-stu-id="f2122-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="f2122-114">*descendant axis*</span><span class="sxs-lookup"><span data-stu-id="f2122-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="f2122-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span><span class="sxs-lookup"><span data-stu-id="f2122-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="f2122-116">*extension indexer*</span><span class="sxs-lookup"><span data-stu-id="f2122-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="f2122-117">Gets the first `name` element from the sequence.</span><span class="sxs-lookup"><span data-stu-id="f2122-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="f2122-118">*value*</span><span class="sxs-lookup"><span data-stu-id="f2122-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="f2122-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span><span class="sxs-lookup"><span data-stu-id="f2122-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="f2122-120">단원 내용</span><span class="sxs-lookup"><span data-stu-id="f2122-120">In This Section</span></span>  
 [<span data-ttu-id="f2122-121">방법: XML 하위 요소 액세스</span><span class="sxs-lookup"><span data-stu-id="f2122-121">How to: Access XML Descendant Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="f2122-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span><span class="sxs-lookup"><span data-stu-id="f2122-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="f2122-123">방법: XML 자식 요소 액세스</span><span class="sxs-lookup"><span data-stu-id="f2122-123">How to: Access XML Child Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 <span data-ttu-id="f2122-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span><span class="sxs-lookup"><span data-stu-id="f2122-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="f2122-125">방법: XML 특성 액세스</span><span class="sxs-lookup"><span data-stu-id="f2122-125">How to: Access XML Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 <span data-ttu-id="f2122-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span><span class="sxs-lookup"><span data-stu-id="f2122-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="f2122-127">방법: XML 네임스페이스 접두사 선언 및 사용</span><span class="sxs-lookup"><span data-stu-id="f2122-127">How to: Declare and Use XML Namespace Prefixes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="f2122-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span><span class="sxs-lookup"><span data-stu-id="f2122-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f2122-129">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f2122-129">Related Sections</span></span>  
 [<span data-ttu-id="f2122-130">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="f2122-130">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/index.md)  
 <span data-ttu-id="f2122-131">Provides links to sections describing the various XML access properties.</span><span class="sxs-lookup"><span data-stu-id="f2122-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="f2122-132">Visual Basic의 LINQ to XML 개요</span><span class="sxs-lookup"><span data-stu-id="f2122-132">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="f2122-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f2122-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="f2122-134">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="f2122-134">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="f2122-135">Provides an introduction to using XML literals in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f2122-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="f2122-136">Visual Basic에서 XML 조작</span><span class="sxs-lookup"><span data-stu-id="f2122-136">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 <span data-ttu-id="f2122-137">Provides links to sections about loading and modifying XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f2122-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="f2122-138">XML</span><span class="sxs-lookup"><span data-stu-id="f2122-138">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="f2122-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f2122-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
