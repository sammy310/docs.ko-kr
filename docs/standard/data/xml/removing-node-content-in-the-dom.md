---
title: DOM에서 노드 내용 제거
ms.date: 03/30/2017
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
ms.openlocfilehash: 7b33ebfea244dbe81879c61be3809adcb2a1f5d3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828870"
---
# <a name="removing-node-content-in-the-dom"></a><span data-ttu-id="bc2ed-102">DOM에서 노드 내용 제거</span><span class="sxs-lookup"><span data-stu-id="bc2ed-102">Removing Node Content in the DOM</span></span>
<span data-ttu-id="bc2ed-103"><xref:System.Xml.XmlCharacterData>에서 상속되는 <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, <xref:System.Xml.XmlSignificantWhitespace> 등의 노드 형식의 경우 노드에서 문자 범위를 제거하는 <xref:System.Xml.XmlCharacterData.DeleteData%2A> 메서드를 사용하여 문자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc2ed-103">For node types that inherit from <xref:System.Xml.XmlCharacterData>, which are the <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, and <xref:System.Xml.XmlSignificantWhitespace> node types, you can remove characters using the <xref:System.Xml.XmlCharacterData.DeleteData%2A> method, which removes a range of characters from the node.</span></span> <span data-ttu-id="bc2ed-104">내용을 완전히 제거하려면 내용이 있는 노드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2ed-104">If you want to remove content completely, you remove the node that contains the content.</span></span> <span data-ttu-id="bc2ed-105">내용은 잘못되었지만 노드를 유지하려면 내용을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2ed-105">If you want to keep the node, but the content is incorrect, then modify the content.</span></span> <span data-ttu-id="bc2ed-106">노드의 내용을 수정하는 방법은 [XML 문서에서 노드, 내용 및 값 수정](modifying-nodes-content-and-values-in-an-xml-document.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc2ed-106">For information on modifying the content of a node, see [Modifying Nodes, Content, and Values in an XML Document](modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc2ed-107">참조</span><span class="sxs-lookup"><span data-stu-id="bc2ed-107">See also</span></span>

- [<span data-ttu-id="bc2ed-108">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="bc2ed-108">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
