---
title: '방법: XML 자식 요소 액세스'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: af5ea809cb0777b16230f20e133764dd5f1f86d9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332334"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a><span data-ttu-id="72153-102">방법: XML 자식 요소 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72153-102">How to: Access XML Child Elements (Visual Basic)</span></span>
<span data-ttu-id="72153-103">이 예제에서는 자식 축 속성을 사용 하 여 XML 요소에 지정 된 이름의 모든 XML 자식 요소에 액세스 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="72153-103">This example shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span> <span data-ttu-id="72153-104">특히 <xref:System.Xml.Linq.XElement.Value%2A> 속성을 사용 하 여 `name` 자식 축 속성이 반환 하는 컬렉션의 첫 번째 요소 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="72153-104">In particular, it uses the <xref:System.Xml.Linq.XElement.Value%2A> property to get the value of the first element in the collection that the `name` child axis property returns.</span></span> <span data-ttu-id="72153-105">`name` 자식 축 속성은 `contact` 개체의 `phone` 이라는 모든 자식 요소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="72153-105">The `name` child axis property gets all child elements named `phone` in the `contact` object.</span></span> <span data-ttu-id="72153-106">또한이 예제에서는 `phone` 자식 축 속성을 사용 하 여 `contact` 개체에 포함 된 `phone` 라는 모든 자식 요소에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="72153-106">This example also uses the `phone` child axis property to access all child elements named `phone` that are contained in the `contact` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72153-107">예제</span><span class="sxs-lookup"><span data-stu-id="72153-107">Example</span></span>  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="72153-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="72153-108">Compiling the Code</span></span>  
 <span data-ttu-id="72153-109">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="72153-109">This example requires:</span></span>  
  
- <span data-ttu-id="72153-110"><xref:System.Xml.Linq> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="72153-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72153-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72153-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="72153-112">XML Child 축 속성</span><span class="sxs-lookup"><span data-stu-id="72153-112">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="72153-113">XML 값 속성</span><span class="sxs-lookup"><span data-stu-id="72153-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="72153-114">Visual Basic에서 XML에 액세스</span><span class="sxs-lookup"><span data-stu-id="72153-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="72153-115">XML</span><span class="sxs-lookup"><span data-stu-id="72153-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
