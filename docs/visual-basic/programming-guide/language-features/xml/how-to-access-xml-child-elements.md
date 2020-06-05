---
title: '방법: XML 자식 요소에 액세스'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 994249801eecc2984947efac9712df0047f076a4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392820"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a><span data-ttu-id="f6029-102">방법: XML 자식 요소 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6029-102">How to: Access XML Child Elements (Visual Basic)</span></span>
<span data-ttu-id="f6029-103">이 예제에서는 자식 축 속성을 사용 하 여 XML 요소에 지정 된 이름의 모든 XML 자식 요소에 액세스 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6029-103">This example shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span> <span data-ttu-id="f6029-104">특히, 속성을 사용 하 여 <xref:System.Xml.Linq.XElement.Value%2A> `name` 자식 축 속성이 반환 하는 컬렉션의 첫 번째 요소 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f6029-104">In particular, it uses the <xref:System.Xml.Linq.XElement.Value%2A> property to get the value of the first element in the collection that the `name` child axis property returns.</span></span> <span data-ttu-id="f6029-105">`name`자식 축 속성은 개체의 이라는 모든 자식 요소를 가져옵니다 `phone` `contact` .</span><span class="sxs-lookup"><span data-stu-id="f6029-105">The `name` child axis property gets all child elements named `phone` in the `contact` object.</span></span> <span data-ttu-id="f6029-106">또한이 예제에서는 자식 축 속성을 사용 하 여 `phone` 개체에 포함 된 이라는 모든 자식 요소에 액세스 `phone` `contact` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6029-106">This example also uses the `phone` child axis property to access all child elements named `phone` that are contained in the `contact` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6029-107">예제</span><span class="sxs-lookup"><span data-stu-id="f6029-107">Example</span></span>  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="f6029-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="f6029-108">Compile the code</span></span>  
 <span data-ttu-id="f6029-109">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f6029-109">This example requires:</span></span>  
  
- <span data-ttu-id="f6029-110"><xref:System.Xml.Linq> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="f6029-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6029-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6029-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f6029-112">XML Child Axis Property</span><span class="sxs-lookup"><span data-stu-id="f6029-112">XML Child Axis Property</span></span>](../../../language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="f6029-113">XML 값 속성</span><span class="sxs-lookup"><span data-stu-id="f6029-113">XML Value Property</span></span>](../../../language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="f6029-114">Visual Basic에서 XML에 액세스</span><span class="sxs-lookup"><span data-stu-id="f6029-114">Accessing XML in Visual Basic</span></span>](accessing-xml.md)
- [<span data-ttu-id="f6029-115">XML</span><span class="sxs-lookup"><span data-stu-id="f6029-115">XML</span></span>](index.md)
