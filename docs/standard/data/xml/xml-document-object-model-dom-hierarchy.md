---
title: XML DOM(문서 개체 모델) 계층 구조
ms.date: 03/30/2017
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
ms.openlocfilehash: 24ef51a18392fe3034e64bd585d879941fca4b95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718360"
---
# <a name="xml-document-object-model-dom-hierarchy"></a><span data-ttu-id="fde45-102">XML DOM(문서 개체 모델) 계층 구조</span><span class="sxs-lookup"><span data-stu-id="fde45-102">XML Document Object Model (DOM) Hierarchy</span></span>

<span data-ttu-id="fde45-103">다음 그림은 관련 위치에 클래스 이름과 함께 괄호 안에 W3C(World Wide Web 컨소시엄) 이름을 표시하여 XML DOM(문서 개체 모델)에 대한 클래스 계층 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fde45-103">The following illustration shows the class hierarchy for the XML Document Object Model (DOM), with the World Wide Web Consortium (W3C) name in parenthesis along with the class name where it is relevant.</span></span>  
  
 <span data-ttu-id="fde45-104">![XML DOM(문서 개체 모델) 계층 구조](media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="fde45-104">![XML Document Object Model &#40;DOM&#41; hierarchy](media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span></span>  
<span data-ttu-id="fde45-105">XML DOM(문서 개체 모델) 계층 구조</span><span class="sxs-lookup"><span data-stu-id="fde45-105">XML Document Object Model (DOM) hierarchy</span></span>  
  
 <span data-ttu-id="fde45-106">다음 클래스는 **XmlNode** 에서 상속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fde45-106">The following classes do not inherit from the **XmlNode**:</span></span>  
  
- <span data-ttu-id="fde45-107">**XmlImplementation**</span><span class="sxs-lookup"><span data-stu-id="fde45-107">**XmlImplementation**</span></span>  
  
- <span data-ttu-id="fde45-108">**XmlNamedNodeMap**</span><span class="sxs-lookup"><span data-stu-id="fde45-108">**XmlNamedNodeMap**</span></span>  
  
- <span data-ttu-id="fde45-109">**XmlNodeList**</span><span class="sxs-lookup"><span data-stu-id="fde45-109">**XmlNodeList**</span></span>  
  
- <span data-ttu-id="fde45-110">**XmlNodeChangedEventArgs**</span><span class="sxs-lookup"><span data-stu-id="fde45-110">**XmlNodeChangedEventArgs**</span></span>  
  
 <span data-ttu-id="fde45-111">**XmlImplementation** 클래스는 XML 문서를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde45-111">The **XmlImplementation** class is used to create an XML document.</span></span> <span data-ttu-id="fde45-112">자세한 내용은 [XML 문서 만들기](xml-document-creation.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde45-112">For more information, see [XML Document Creation](xml-document-creation.md).</span></span>  
  
 <span data-ttu-id="fde45-113">**XmlNamedNodeMap** 클래스는 정렬되지 않은 노드 집합을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="fde45-113">The **XmlNamedNodeMap** class handles an unordered set of nodes.</span></span> <span data-ttu-id="fde45-114">자세한 내용은 [이름 또는 인덱스별로 정렬되지 않은 노드 검색](unordered-node-retrieval-by-name-or-index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde45-114">For more information, see [Unordered Node Retrieval by Name or Index](unordered-node-retrieval-by-name-or-index.md).</span></span>  
  
 <span data-ttu-id="fde45-115">**XmlNodeList** 클래스는 정렬된 노드 목록을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="fde45-115">The **XmlNodeList** class handles an ordered list of nodes.</span></span> <span data-ttu-id="fde45-116">자세한 내용은 [인덱스를 사용한 정렬된 노드 검색](ordered-node-retrieval-by-index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde45-116">For more information, see [Ordered Node Retrieval by Index](ordered-node-retrieval-by-index.md).</span></span>  
  
 <span data-ttu-id="fde45-117">**XmlNodeChangedEventArgs** 클래스는 **XmlDocument** 에 등록된 이벤트 처리기를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="fde45-117">The **XmlNodeChangedEventArgs** class handles event handlers registered on the **XmlDocument**.</span></span> <span data-ttu-id="fde45-118">자세한 내용은 [XmlNodeChangedEventArgs를 사용한 XML 문서의 이벤트 처리](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde45-118">For more information, see [Event Handling in an XML Document using the XmlNodeChangedEventArgs](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span></span>  
  
 <span data-ttu-id="fde45-119">**XmlLinkedNode** 클래스는 **XmlNode** 에서 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="fde45-119">The **XmlLinkedNode** class inherits from **XmlNode**.</span></span> <span data-ttu-id="fde45-120">이 클래스의 용도는 **XmlNode** 의 **PreviousSibling** 및 **NextSibling** 메서드를 재정의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fde45-120">Its purpose is to override two methods from **XmlNode**: the **PreviousSibling** and **NextSibling** methods.</span></span> <span data-ttu-id="fde45-121">그런 다음, 이처럼 재정의된 메서드를 서로 계층 구조를 이루는 형제 클래스인 **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** 및 **XmlProcessingInstruction** 에서 상속하여 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fde45-121">These overridden methods are then inherited and used by **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, and **XmlProcessingInstruction**, which are classes that have previous and next siblings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fde45-122">참조</span><span class="sxs-lookup"><span data-stu-id="fde45-122">See also</span></span>

- [<span data-ttu-id="fde45-123">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="fde45-123">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
