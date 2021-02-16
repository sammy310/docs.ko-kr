---
description: '자세한 정보: XML 리터럴의 공백 (Visual Basic)'
title: XML 리터럴의 공백
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 9b4134626c0ad1f7f4be2923573eb6058fa7687f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428118"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="1de3c-103">XML 리터럴의 공백(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1de3c-103">White Space in XML Literals (Visual Basic)</span></span>

<span data-ttu-id="1de3c-104">Visual Basic 컴파일러는 개체를 만들 때 XML 리터럴의 유효 공백 문자만을 포함 합니다 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1de3c-104">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="1de3c-105">무효 공백 문자는 통합 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1de3c-105">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="1de3c-106">중요 및 무효 공백</span><span class="sxs-lookup"><span data-stu-id="1de3c-106">Significant and Insignificant White Space</span></span>  

 <span data-ttu-id="1de3c-107">XML 리터럴의 공백 문자는 다음 세 가지 영역 에서만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de3c-107">White space characters in XML literals are significant in only three areas:</span></span>  
  
- <span data-ttu-id="1de3c-108">특성 값에 있는 경우</span><span class="sxs-lookup"><span data-stu-id="1de3c-108">When they are in an attribute value.</span></span>  
  
- <span data-ttu-id="1de3c-109">요소가 요소의 텍스트 내용에 포함 되 고 텍스트에 다른 문자가 포함 된 경우</span><span class="sxs-lookup"><span data-stu-id="1de3c-109">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
- <span data-ttu-id="1de3c-110">요소가 요소의 텍스트 콘텐츠에 대 한 포함 식에 있는 경우</span><span class="sxs-lookup"><span data-stu-id="1de3c-110">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="1de3c-111">그렇지 않으면 컴파일러는 공백 문자를 중요 하지 않은 것으로 처리 하 고이를 리터럴의 개체에 포함 하지 않습니다 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1de3c-111">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="1de3c-112">XML 리터럴에 의미 없는 공백을 포함 하려면 공백이 있는 문자열 리터럴이 포함 된 포함 식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de3c-112">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1de3c-113">`xml:space`특성이 XML 요소 리터럴에 표시 되는 경우 Visual Basic 컴파일러는 개체에 특성을 포함 <xref:System.Xml.Linq.XElement> 하지만이 특성을 추가 해도 컴파일러에서 공백을 처리 하는 방법은 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1de3c-113">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1de3c-114">예제</span><span class="sxs-lookup"><span data-stu-id="1de3c-114">Examples</span></span>  

 <span data-ttu-id="1de3c-115">다음 예제에는 외부 및 내부 라는 두 개의 XML 요소가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de3c-115">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="1de3c-116">두 요소 모두 텍스트 내용에 공백을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de3c-116">Both elements contain white space in their text content.</span></span> <span data-ttu-id="1de3c-117">외부 요소의 공백은 공백과 XML 요소만 포함 하기 때문에 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1de3c-117">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="1de3c-118">내부 요소의 공백은 공백과 텍스트를 포함 하기 때문에 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de3c-118">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 <span data-ttu-id="1de3c-119">이 코드는 실행 될 때 다음 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de3c-119">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1de3c-120">추가 정보</span><span class="sxs-lookup"><span data-stu-id="1de3c-120">See also</span></span>

- [<span data-ttu-id="1de3c-121">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="1de3c-121">Creating XML in Visual Basic</span></span>](creating-xml.md)
