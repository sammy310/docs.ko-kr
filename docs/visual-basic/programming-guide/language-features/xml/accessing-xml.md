---
description: '자세한 정보: Visual Basic에서 XML 액세스'
title: XML에 액세스
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 2d77b2aa5f4136095ce5684976fe3ba03be7c28c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462661"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="05069-103">Visual Basic에서 XML에 액세스</span><span class="sxs-lookup"><span data-stu-id="05069-103">Accessing XML in Visual Basic</span></span>

<span data-ttu-id="05069-104">Visual Basic는 구조에 액세스 하 고 탐색 하기 위한 XML 축 속성을 제공 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="05069-104">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="05069-105">이러한 속성은 XML 이름을 지정 하 여 요소 및 특성에 액세스할 수 있도록 특수 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05069-105">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="05069-106">다음 표에서는 Visual Basic의 XML 요소와 특성에 액세스할 수 있게 해 주는 언어 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05069-106">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="05069-107">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="05069-107">XML Axis Properties</span></span>  
  
|<span data-ttu-id="05069-108">속성 설명</span><span class="sxs-lookup"><span data-stu-id="05069-108">Property description</span></span>|<span data-ttu-id="05069-109">예제</span><span class="sxs-lookup"><span data-stu-id="05069-109">Example</span></span>|<span data-ttu-id="05069-110">설명</span><span class="sxs-lookup"><span data-stu-id="05069-110">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="05069-111">*child 축*</span><span class="sxs-lookup"><span data-stu-id="05069-111">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="05069-112">`phone`요소의 자식 요소인 모든 요소를 가져옵니다 `contact` .</span><span class="sxs-lookup"><span data-stu-id="05069-112">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="05069-113">*특성 축*</span><span class="sxs-lookup"><span data-stu-id="05069-113">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="05069-114">요소의 모든 `type` 특성을 가져옵니다 `phone` .</span><span class="sxs-lookup"><span data-stu-id="05069-114">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="05069-115">*descendant 축*</span><span class="sxs-lookup"><span data-stu-id="05069-115">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="05069-116">발생 한 `name` `contacts` 계층의 깊이에 관계 없이 요소의 모든 요소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05069-116">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="05069-117">*확장 인덱서*</span><span class="sxs-lookup"><span data-stu-id="05069-117">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="05069-118">시퀀스에서 첫 번째 요소를 가져옵니다 `name` .</span><span class="sxs-lookup"><span data-stu-id="05069-118">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="05069-119">*value*</span><span class="sxs-lookup"><span data-stu-id="05069-119">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="05069-120">시퀀스에서 첫 번째 개체의 문자열 표현을 가져오거나, 시퀀스가 비어 있는 경우에는입니다 `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="05069-120">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="05069-121">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="05069-121">In This Section</span></span>  

 [<span data-ttu-id="05069-122">방법: XML 하위 요소에 액세스</span><span class="sxs-lookup"><span data-stu-id="05069-122">How to: Access XML Descendant Elements</span></span>](how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="05069-123">하위 축 속성을 사용 하 여 지정 된 이름을 가진 모든 XML 요소에 액세스 하 고 지정 된 XML 요소에 포함 된 모든 XML 요소에 액세스 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05069-123">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="05069-124">방법: XML 자식 요소에 액세스</span><span class="sxs-lookup"><span data-stu-id="05069-124">How to: Access XML Child Elements</span></span>](how-to-access-xml-child-elements.md)  
 <span data-ttu-id="05069-125">자식 축 속성을 사용 하 여 XML 요소에 지정 된 이름의 모든 XML 자식 요소에 액세스 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05069-125">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="05069-126">방법: XML 특성에 액세스</span><span class="sxs-lookup"><span data-stu-id="05069-126">How to: Access XML Attributes</span></span>](how-to-access-xml-attributes.md)  
 <span data-ttu-id="05069-127">특성 축 속성을 사용 하 여 XML 요소에 지정 된 이름의 모든 XML 특성에 액세스 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05069-127">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="05069-128">방법: XML 네임스페이스 접두사 선언 및 사용</span><span class="sxs-lookup"><span data-stu-id="05069-128">How to: Declare and Use XML Namespace Prefixes</span></span>](how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="05069-129">XML 네임 스페이스 접두사를 선언 하 고이 접두사를 사용 하 여 XML 요소를 만들고 액세스 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05069-129">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="05069-130">관련 단원</span><span class="sxs-lookup"><span data-stu-id="05069-130">Related Sections</span></span>  

 [<span data-ttu-id="05069-131">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="05069-131">XML Axis Properties</span></span>](../../../language-reference/xml-axis/index.md)  
 <span data-ttu-id="05069-132">다양 한 XML 액세스 속성을 설명 하는 섹션에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="05069-132">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="05069-133">Visual Basic의 LINQ to XML 개요</span><span class="sxs-lookup"><span data-stu-id="05069-133">Overview of LINQ to XML in Visual Basic</span></span>](overview-of-linq-to-xml.md)  
 <span data-ttu-id="05069-134">Visual Basic에서를 사용 하는 방법을 소개 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="05069-134">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="05069-135">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="05069-135">Creating XML in Visual Basic</span></span>](creating-xml.md)  
 <span data-ttu-id="05069-136">Visual Basic에서 XML 리터럴을 사용 하는 방법을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="05069-136">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="05069-137">Visual Basic에서 XML 조작</span><span class="sxs-lookup"><span data-stu-id="05069-137">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)  
 <span data-ttu-id="05069-138">Visual Basic에서 XML을 로드 하 고 수정 하는 방법에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="05069-138">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="05069-139">XML</span><span class="sxs-lookup"><span data-stu-id="05069-139">XML</span></span>](index.md)  
 <span data-ttu-id="05069-140">Visual Basic에서를 사용 하는 방법을 설명 하는 섹션에 대 한 링크를 제공 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="05069-140">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
