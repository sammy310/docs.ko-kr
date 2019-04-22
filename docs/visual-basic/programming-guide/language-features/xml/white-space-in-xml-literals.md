---
title: XML 리터럴의 공백(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 08be345557d10a528aa03234883eba1b3a31beaa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832759"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="3fa60-102">XML 리터럴의 공백(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3fa60-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="3fa60-103">Visual Basic 컴파일러를 만들 때 XML 리터럴에서 유효 공백 문자만 포함 된 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3fa60-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="3fa60-104">불필요 한 공백 문자는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa60-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="3fa60-105">유효 공백과 무효 공백</span><span class="sxs-lookup"><span data-stu-id="3fa60-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="3fa60-106">만 세 가지 영역에서 XML 리터럴의 공백 문자 사항이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa60-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
-   <span data-ttu-id="3fa60-107">특성 값에 있을 때.</span><span class="sxs-lookup"><span data-stu-id="3fa60-107">When they are in an attribute value.</span></span>  
  
-   <span data-ttu-id="3fa60-108">요소의 텍스트 콘텐츠 일부가 텍스트에도 다른 문자가 시점과 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa60-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
-   <span data-ttu-id="3fa60-109">요소의 텍스트 콘텐츠에 대 한 포함된 식을에 있을 때.</span><span class="sxs-lookup"><span data-stu-id="3fa60-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="3fa60-110">그렇지 않으면 컴파일러를 불필요 한 공백 문자를 처리 하 고에 포함 되지 않습니다는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 리터럴의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3fa60-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="3fa60-111">무효 공백은 리터럴 XML에 포함 하려면 공백을 사용 하 여 리터럴 문자열을 포함 하는 포함 된 식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa60-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fa60-112">경우는 `xml:space` XML 요소 리터럴에 표시 되는 특성, Visual Basic 컴파일러에서 특성을 포함 합니다 <xref:System.Xml.Linq.XElement> 개체가 아니라이 특성에 컴파일러는 공백 문자를 처리 하는 방법을 변경 하지 않습니다 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa60-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3fa60-113">예제</span><span class="sxs-lookup"><span data-stu-id="3fa60-113">Examples</span></span>  
 <span data-ttu-id="3fa60-114">다음 예제에서는 두 개의 XML 요소를 외부 및 내부를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa60-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="3fa60-115">두 요소 텍스트 내용에 공백이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa60-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="3fa60-116">공백 및 XML 요소가 포함 되어 있으므로 외부 요소에서 공백을 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa60-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="3fa60-117">요소의 내부에 공백을 공백 및 텍스트 있기 때문에 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa60-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 <span data-ttu-id="3fa60-118">를 실행 하는 경우이 코드는 다음 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa60-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3fa60-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="3fa60-119">See also</span></span>

- [<span data-ttu-id="3fa60-120">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="3fa60-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
