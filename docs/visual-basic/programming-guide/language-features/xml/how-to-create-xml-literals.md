---
title: '방법: XML 리터럴 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: e3af5185d2c2106e6a696a6569ef59897d0f1fe1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332996"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="ed28e-102">방법: XML 리터럴 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed28e-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="ed28e-103">XML 리터럴을 사용 하 여 코드에서 직접 XML 문서, 조각 또는 요소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed28e-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="ed28e-104">이 항목의 예제에서는 세 개의 자식 요소가 있는 XML 요소를 만드는 방법 및 XML 문서를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed28e-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="ed28e-105">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Api를 사용 하 여 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed28e-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="ed28e-106">자세한 내용은 <xref:System.Xml.Linq.XElement>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed28e-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="ed28e-107">XML 요소를 만들려면</span><span class="sxs-lookup"><span data-stu-id="ed28e-107">To create an XML element</span></span>  
  
- <span data-ttu-id="ed28e-108">실제 XML 구문과 동일한 XML 리터럴 구문을 사용 하 여 XML 인라인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed28e-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     <span data-ttu-id="ed28e-109">코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed28e-109">Run the code.</span></span> <span data-ttu-id="ed28e-110">이 코드의 출력이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed28e-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="ed28e-111">XML 문서를 만들려면</span><span class="sxs-lookup"><span data-stu-id="ed28e-111">To create an XML document</span></span>  
  
- <span data-ttu-id="ed28e-112">XML 문서 인라인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed28e-112">Create the XML document inline.</span></span> <span data-ttu-id="ed28e-113">다음 코드는 리터럴 구문, XML 선언, 처리 명령, 주석 및 다른 요소를 포함 하는 요소를 포함 하는 XML 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed28e-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     <span data-ttu-id="ed28e-114">코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed28e-114">Run the code.</span></span> <span data-ttu-id="ed28e-115">이 코드의 출력이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed28e-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="ed28e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed28e-116">See also</span></span>

- [<span data-ttu-id="ed28e-117">XML</span><span class="sxs-lookup"><span data-stu-id="ed28e-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="ed28e-118">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="ed28e-118">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="ed28e-119">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="ed28e-119">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="ed28e-120">XML 문서 리터럴</span><span class="sxs-lookup"><span data-stu-id="ed28e-120">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
