---
title: DOM에 엔터티 선언 및 엔터티 참조 읽어오기
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 86dba977-5cc4-4567-964f-027ffabc47b2
ms.openlocfilehash: fa650e75d7661eeafea74146f5cbb61878978575
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710403"
---
# <a name="reading-entity-declarations-and-entity-references-into-the-dom"></a><span data-ttu-id="dbe34-102">DOM에 엔터티 선언 및 엔터티 참조 읽어오기</span><span class="sxs-lookup"><span data-stu-id="dbe34-102">Reading Entity Declarations and Entity References into the DOM</span></span>
<span data-ttu-id="dbe34-103">엔터티는 XML에서 내용 또는 태그 대신 사용되는 이름을 나타내는 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-103">An entity is a declaration that states a name to be used in the XML in place of content or markup.</span></span> <span data-ttu-id="dbe34-104">엔터티는 두 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-104">There are two parts to entities.</span></span> <span data-ttu-id="dbe34-105">먼저 엔터티 선언을 사용하여 이름을 대체 내용에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-105">First, you must tie a name to the replacement content using an entity declaration.</span></span> <span data-ttu-id="dbe34-106">엔터티 선언은 DTD(문서 종류 정의) 또는 XML 스키마에 `<!ENTITY name "value">` 구문을 사용하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-106">An entity declaration is created by using the `<!ENTITY name "value">` syntax in a document type definition (DTD) or XML schema.</span></span> <span data-ttu-id="dbe34-107">그러면 엔터티 선언에 정의된 이름이 XML에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-107">Secondly, the name defined in the entity declaration is subsequently used in the XML.</span></span> <span data-ttu-id="dbe34-108">XML에서 사용될 경우 이 이름을 엔터티 참조라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-108">When used in the XML, it is called an entity reference.</span></span> <span data-ttu-id="dbe34-109">예를 들어, 다음 엔터티 선언은 "Microsoft Press"라는 내용과 연결될 `publisher`라는 이름의 엔터티를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-109">For example, the following entity declaration declares an entity of the name `publisher` being associated with the content of "Microsoft Press".</span></span>  
  
```xml  
<!ENTITY publisher "Microsoft Press">  
```  
  
 <span data-ttu-id="dbe34-110">다음 예제에서는 XML에서 엔터티 참조로 이 엔터티 선언을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-110">The following example shows the use of this entity declaration in XML as an entity reference.</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="dbe34-111">문서가 메모리에 로드되면 일부 파서는 자동으로 엔터티를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-111">Some parsers automatically expand entities when a document is loaded into memory.</span></span> <span data-ttu-id="dbe34-112">따라서 XML을 메모리에 읽어오면 엔터티 선언이 기억되고 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-112">Therefore, when the XML is being read into memory, entity declarations are remembered and saved.</span></span> <span data-ttu-id="dbe34-113">그런 다음 파서가 일반 엔터티 참조를 식별하는 `&;` 문자를 발견하면 엔터티 선언 테이블에서 해당 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-113">When the parser subsequently encounters `&;` characters, which identify a general entity reference, the parser looks up that name in an entity declaration table.</span></span> <span data-ttu-id="dbe34-114">`&publisher;` 참조는 해당 참조가 나타내는 내용으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-114">The reference, `&publisher;` is replaced by the content that it represents.</span></span> <span data-ttu-id="dbe34-115">다음 XML을 사용한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-115">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="dbe34-116">엔터티 참조를 확장하고 `&publisher;`를 Microsoft Press라는 내용으로 바꿔 다음과 같은 확장된 XML을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-116">expanding the entity reference and replacing the `&publisher;` with the Microsoft Press content gives the following expanded XML.</span></span>  
  
 <span data-ttu-id="dbe34-117">**출력**</span><span class="sxs-lookup"><span data-stu-id="dbe34-117">**Output**</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by Microsoft Press</pubinfo>  
```  
  
 <span data-ttu-id="dbe34-118">엔터티에는 여러 종류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-118">There are many kinds of entities.</span></span> <span data-ttu-id="dbe34-119">다음 다이어그램은 엔터티 형식과 용어의 분류를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-119">The following diagram shows the breakdown of entity types and terminology.</span></span>  
  
 <span data-ttu-id="dbe34-120">![엔터티 형식 계층 구조의 순서도](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="dbe34-120">![flow chart of entity type hierarchy](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")</span></span>  
  
 <span data-ttu-id="dbe34-121">기본적으로 이 XML DOM(문서 개체 모델)의 Microsoft .NET Framework 구현은 XML이 로드될 때 엔터티 참조를 유지하고 엔터티를 확장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-121">The default for the Microsoft .NET Framework implementation of the XML Document Object Model (DOM) is to preserve the entities references and not expand the entities when the XML is loaded.</span></span> <span data-ttu-id="dbe34-122">즉, 문서를 DOM에 로드할 때 참조 변수 `&publisher;`를 포함하는 **XmlEntityReference** 노드가 생성되며 자식 노드는 DTD에 선언된 엔터티의 내용을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-122">The implication of this is that as a document is loaded in the DOM, an **XmlEntityReference** node containing the reference variable `&publisher;` is created, with child nodes representing the content in the entity declared in the DTD.</span></span>  
  
 <span data-ttu-id="dbe34-123">다음 다이어그램은 `<!ENTITY publisher "Microsoft Press">` 엔터티 선언을 사용하여 해당 선언에서 생성된 **XmlEntity** 및 **XmlText** 노드를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-123">Using the `<!ENTITY publisher "Microsoft Press">` entity declaration, the following diagram shows the **XmlEntity** and **XmlText** nodes created from this declaration.</span></span>  
  
 <span data-ttu-id="dbe34-124">![엔터티 선언에서 만든 노드](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span><span class="sxs-lookup"><span data-stu-id="dbe34-124">![nodes created from entity declaration](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span></span>  
  
 <span data-ttu-id="dbe34-125">엔터티 참조가 확장되는 경우와 그렇지 않은 경우에 메모리의 DOM 트리에 생성되는 노드가 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-125">The differences when entity references are expanded and when they are not makes a difference in what nodes are generated in the DOM tree, in memory.</span></span> <span data-ttu-id="dbe34-126">생성되는 노드의 차이점은 [엔터티 참조 유지](../../../../docs/standard/data/xml/entity-references-are-preserved.md) 및 [유지되지 않고 확장되는 엔터티 참조](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md) 항목에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe34-126">The difference in the nodes that are generated is explained in the topics [Entity References are Preserved](../../../../docs/standard/data/xml/entity-references-are-preserved.md) and [Entity References are Expanded and Not Preserved](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe34-127">참조</span><span class="sxs-lookup"><span data-stu-id="dbe34-127">See also</span></span>

- [<span data-ttu-id="dbe34-128">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="dbe34-128">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
