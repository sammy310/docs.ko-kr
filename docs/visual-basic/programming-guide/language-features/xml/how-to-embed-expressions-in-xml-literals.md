---
description: '자세한 정보: 방법: XML 리터럴에 식 포함 (Visual Basic)'
title: '방법: XML 리터럴에 식 포함'
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 18bc6164c4466532956f1a5df70c1ff2a8dbbfd5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480052"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="96e04-103">방법: XML 리터럴에 식 포함(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96e04-103">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>

<span data-ttu-id="96e04-104">XML 리터럴을 포함 된 식과 결합 하 여 런타임에 생성 된 내용이 포함 된 XML 문서, 조각 또는 요소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96e04-104">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="96e04-105">다음 예제에서는 포함 식을 사용 하 여 런타임에 요소 내용, 특성 및 요소 이름을 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96e04-105">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="96e04-106">포함 식의 구문은 `<%=` `exp` `%>` ASP.NET에서 사용 하는 것과 동일한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="96e04-106">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that ASP.NET uses.</span></span> <span data-ttu-id="96e04-107">자세한 내용은 [XML의 포함 식](embedded-expressions-in-xml.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96e04-107">For more information, see [Embedded Expressions in XML](embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="96e04-108">Api를 사용 하 여 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체를 만들 수도 있습니다 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96e04-108">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="96e04-109">자세한 내용은 <xref:System.Xml.Linq.XElement>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96e04-109">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="96e04-110">프로시저</span><span class="sxs-lookup"><span data-stu-id="96e04-110">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="96e04-111">텍스트를 요소 콘텐츠로 삽입 하려면</span><span class="sxs-lookup"><span data-stu-id="96e04-111">To insert text as element content</span></span>  
  
- <span data-ttu-id="96e04-112">다음 예제에서는 `contactName` 여는 이름과 닫는 name 요소 사이에 변수에 포함 된 텍스트를 삽입 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96e04-112">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     <span data-ttu-id="96e04-113">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="96e04-113">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="96e04-114">텍스트를 특성 값으로 삽입 하려면</span><span class="sxs-lookup"><span data-stu-id="96e04-114">To insert text as an attribute value</span></span>  
  
- <span data-ttu-id="96e04-115">다음 예에서는 변수에 포함 된 텍스트를 특성 값으로 삽입 하는 방법을 보여 줍니다 `phoneType` `type` .</span><span class="sxs-lookup"><span data-stu-id="96e04-115">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     <span data-ttu-id="96e04-116">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="96e04-116">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="96e04-117">요소 이름에 텍스트를 삽입 하려면</span><span class="sxs-lookup"><span data-stu-id="96e04-117">To insert text for an element name</span></span>  
  
- <span data-ttu-id="96e04-118">다음 예제에서는 변수에 포함 된 텍스트를 요소의 이름으로 삽입 하는 방법을 보여 줍니다 `elementName` .</span><span class="sxs-lookup"><span data-stu-id="96e04-118">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="96e04-119">이 기술을 사용 하 여 요소를 만들 때 태그를 사용 하 여 요소를 닫아야 합니다 \</> .</span><span class="sxs-lookup"><span data-stu-id="96e04-119">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     <span data-ttu-id="96e04-120">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="96e04-120">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="96e04-121">참조</span><span class="sxs-lookup"><span data-stu-id="96e04-121">See also</span></span>

- [<span data-ttu-id="96e04-122">방법: XML 리터럴 만들기</span><span class="sxs-lookup"><span data-stu-id="96e04-122">How to: Create XML Literals</span></span>](how-to-create-xml-literals.md)
- [<span data-ttu-id="96e04-123">XML의 포함 식</span><span class="sxs-lookup"><span data-stu-id="96e04-123">Embedded Expressions in XML</span></span>](embedded-expressions-in-xml.md)
- [<span data-ttu-id="96e04-124">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="96e04-124">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="96e04-125">XML</span><span class="sxs-lookup"><span data-stu-id="96e04-125">XML</span></span>](index.md)
