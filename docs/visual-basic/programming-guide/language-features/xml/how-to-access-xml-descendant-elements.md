---
title: '방법: XML 하위 요소에 액세스'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 03c403aa3c187b0b9d2006104eccaa1f9cd8aec5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392638"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="c8d36-102">방법: XML 하위 요소 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8d36-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="c8d36-103">이 예제에서는 하위 항목 축 속성을 사용 하 여 지정 된 이름의 xml 요소에 포함 된 모든 XML 요소에 액세스 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8d36-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="c8d36-104">특히, 속성을 사용 하 여 `Value` `name` 하위 항목 축 속성이 반환 하는 컬렉션의 첫 번째 요소 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c8d36-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="c8d36-105">`name`하위 축 속성은 개체에 포함 된 이라는 모든 요소 `name` 를 가져옵니다 `contacts` .</span><span class="sxs-lookup"><span data-stu-id="c8d36-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="c8d36-106">또한이 예제에서는 `phone` 하위 항목 축 속성을 사용 하 여 `phone` 개체에 포함 된 이라는 모든 하위 요소에 액세스 합니다 `contacts` .</span><span class="sxs-lookup"><span data-stu-id="c8d36-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8d36-107">예제</span><span class="sxs-lookup"><span data-stu-id="c8d36-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="c8d36-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c8d36-108">Compile the code</span></span>  
 <span data-ttu-id="c8d36-109">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d36-109">This example requires:</span></span>  
  
- <span data-ttu-id="c8d36-110"><xref:System.Xml.Linq> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="c8d36-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d36-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8d36-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c8d36-112">XML Descendant Axis Property</span><span class="sxs-lookup"><span data-stu-id="c8d36-112">XML Descendant Axis Property</span></span>](../../../language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="c8d36-113">XML 값 속성</span><span class="sxs-lookup"><span data-stu-id="c8d36-113">XML Value Property</span></span>](../../../language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="c8d36-114">Visual Basic에서 XML에 액세스</span><span class="sxs-lookup"><span data-stu-id="c8d36-114">Accessing XML in Visual Basic</span></span>](accessing-xml.md)
- [<span data-ttu-id="c8d36-115">XML</span><span class="sxs-lookup"><span data-stu-id="c8d36-115">XML</span></span>](index.md)
