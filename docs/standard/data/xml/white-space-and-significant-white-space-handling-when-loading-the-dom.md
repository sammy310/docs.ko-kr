---
title: DOM을 로드할 경우 공백 문자 및 유효 공백 문자 처리
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
ms.openlocfilehash: 834644a07d790401a1131d6d901f144ef90dc495
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710026"
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a><span data-ttu-id="2a9d2-102">DOM을 로드할 경우 공백 문자 및 유효 공백 문자 처리</span><span class="sxs-lookup"><span data-stu-id="2a9d2-102">White Space and Significant White Space Handling when Loading the DOM</span></span>
<span data-ttu-id="2a9d2-103">문서를 로드할 때 이 옵션을 설정하여 공백을 유지하고 문서 트리에 **XmlWhitespace** 노드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a9d2-103">When loading the document, you can set the option to preserve white space and create **XmlWhitespace** nodes in the document tree.</span></span> <span data-ttu-id="2a9d2-104">공백 노드를 만들려면 **PreserveWhitespace** 속성을 true로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9d2-104">To create white space nodes, set the **PreserveWhitespace** property to true.</span></span> <span data-ttu-id="2a9d2-105">이 속성이 기본값인 **false**로 설정되면 공백 노드가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a9d2-105">If the property is set to **false**, which is the default, white space nodes are not created.</span></span> <span data-ttu-id="2a9d2-106">**PreserveWhitespace** 플래그 설정에 관계없이 항상 유효 공백 노드가 유지되며 이 데이터를 나타내는 **XmlSignificantWhitespace** 노드가 메모리에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a9d2-106">Significant white spaces nodes are always preserved, and **XmlSignificantWhitespace** nodes are always created in memory to represent this data, regardless of the setting of the **PreserveWhitespace** flag.</span></span>  
  
 <span data-ttu-id="2a9d2-107">판독기에서 문서가 로드되면 **XmlDocument** 클래스의 **PreserveWhitespace** 플래그 속성 설정은 **XmlTextReader**의 **WhitespaceHandling** 속성이 **WhitespaceHandling.None**으로 설정되지 않은 경우에만 **XmlWhitespace** 노드 생성에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a9d2-107">If the document is loaded from a reader, then setting of the **PreserveWhitespace** flag property on the **XmlDocument** class affects the creation of **XmlWhitespace** nodes only when the **WhitespaceHandling** property on the **XmlTextReader** is not set to **WhitespaceHandling.None**.</span></span> <span data-ttu-id="2a9d2-108">이것은 판독기의 **WhitespaceHandling** 속성 값이 **XmlDocument**의 해당 플래그 설정보다 우선하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2a9d2-108">It is the value of the **WhitespaceHandling** property on the reader that takes precedence over the setting of that flag on the **XmlDocument**.</span></span> <span data-ttu-id="2a9d2-109">**XmlSignificantWhitespace**에 대한 자세한 내용은 <xref:System.Xml.XmlSignificantWhitespace>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a9d2-109">For more information on **XmlSignificantWhitespace**, see <xref:System.Xml.XmlSignificantWhitespace>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9d2-110">참조</span><span class="sxs-lookup"><span data-stu-id="2a9d2-110">See also</span></span>

- [<span data-ttu-id="2a9d2-111">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="2a9d2-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
