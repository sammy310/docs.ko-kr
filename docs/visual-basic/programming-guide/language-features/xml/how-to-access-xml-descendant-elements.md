---
title: '방법: XML 하위 요소 액세스 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: bfbf849bd296f639f03580346e4a9c52ce000abd
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832218"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="08e93-102">방법: XML 하위 요소 액세스 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08e93-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="08e93-103">이 예제는 하위 항목 축 속성을 사용 하 여 지정 된 이름이 있는 XML 요소 아래에 포함 된 모든 XML 요소에 액세스 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08e93-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="08e93-104">사용 하 여 특히 합니다 `Value` 속성을 하는 컬렉션의 첫 번째 요소의 값을 가져옵니다는 `name` 하위 축 속성에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="08e93-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="08e93-105">합니다 `name` 하위 축 속성 이라는 모든 요소를 가져옵니다 `name` 에 포함 되어 있는 `contacts` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="08e93-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="08e93-106">또한이 예제에서는 합니다 `phone` 이라는 모든 하위 요소를 액세스 하는 하위 항목 축 속성 `phone` 에 포함 되어 있는 `contacts` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="08e93-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08e93-107">예제</span><span class="sxs-lookup"><span data-stu-id="08e93-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="08e93-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="08e93-108">Compiling the Code</span></span>  
 <span data-ttu-id="08e93-109">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="08e93-109">This example requires:</span></span>  
  
-   <span data-ttu-id="08e93-110"><xref:System.Xml.Linq> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="08e93-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08e93-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="08e93-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="08e93-112">XML Descendant 축 속성</span><span class="sxs-lookup"><span data-stu-id="08e93-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="08e93-113">XML 값 속성</span><span class="sxs-lookup"><span data-stu-id="08e93-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="08e93-114">Visual Basic에서 XML에 액세스</span><span class="sxs-lookup"><span data-stu-id="08e93-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="08e93-115">XML</span><span class="sxs-lookup"><span data-stu-id="08e93-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
