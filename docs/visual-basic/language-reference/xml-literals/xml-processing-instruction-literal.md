---
title: XML 처리 명령 리터럴(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 3fbb16a4d47801b671d37566573215d3a57afff1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938608"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="37aba-102">XML 처리 명령 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37aba-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="37aba-103">리터럴 나타내는 <xref:System.Xml.Linq.XProcessingInstruction> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37aba-104">구문</span><span class="sxs-lookup"><span data-stu-id="37aba-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="37aba-105">요소</span><span class="sxs-lookup"><span data-stu-id="37aba-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="37aba-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="37aba-106">Required.</span></span> <span data-ttu-id="37aba-107">XML 처리 명령 리터럴의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="37aba-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="37aba-108">Required.</span></span> <span data-ttu-id="37aba-109">이름을 나타내는 응용 프로그램 처리 명령의 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="37aba-110">"Xml" 또는 "XML"로 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="37aba-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-111">Optional.</span></span> <span data-ttu-id="37aba-112">응용 프로그램 대상으로 지정 하는 방법을 나타내는 문자열 `piName` XML 문서를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="37aba-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="37aba-113">Required.</span></span> <span data-ttu-id="37aba-114">처리 명령의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37aba-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="37aba-115">Return Value</span></span>  
 <span data-ttu-id="37aba-116"><xref:System.Xml.Linq.XProcessingInstruction> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37aba-117">설명</span><span class="sxs-lookup"><span data-stu-id="37aba-117">Remarks</span></span>  
 <span data-ttu-id="37aba-118">XML 처리 명령 리터럴 응용 프로그램 XML 문서를 처리 해야 하는 방법을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="37aba-119">XML 문서를 로드 하는 응용 프로그램을 하는 경우 응용 프로그램 XML 처리 명령이 문서를 처리 하는 방법을 결정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="37aba-120">응용 프로그램의 의미를 해석 `piName` 고 `piData`입니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="37aba-121">리터럴 XML 문서에는 XML 처리 명령 하는 유사한 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="37aba-122">자세한 내용은 [XML 문서 리터럴](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37aba-123">`piName` 요소는 XML 1.0 사양에는 해당 식별자를 예약 하기 때문에 문자열 "xml" 또는 "XML"로 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="37aba-124">XML 처리 명령 리터럴 변수에 할당할 수도 있고 리터럴 XML 문서에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37aba-125">XML 리터럴의 줄 연속 문자가 필요 없이 여러 줄으로 나누어 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="37aba-126">이 옵션을 사용 하면 XML 문서에서 콘텐츠를 복사 하 고 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="37aba-127">Visual Basic 컴파일러는 XML 처리 명령 리터럴의 호출으로 변환 된 <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37aba-128">예제</span><span class="sxs-lookup"><span data-stu-id="37aba-128">Example</span></span>  
 <span data-ttu-id="37aba-129">다음 예제에서는 XML 문서에 대 한 스타일 시트를 식별 하는 처리 명령을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="37aba-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="37aba-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="37aba-130">See also</span></span>

- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="37aba-131">XML 문서 리터럴</span><span class="sxs-lookup"><span data-stu-id="37aba-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="37aba-132">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="37aba-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="37aba-133">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="37aba-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
