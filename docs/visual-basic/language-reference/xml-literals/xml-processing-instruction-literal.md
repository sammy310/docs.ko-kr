---
title: XML 처리 명령 리터럴
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 3d18e58cb643fa075f6eb08eb6fe909d27a6737b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866402"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="6f291-102">XML 처리 명령 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f291-102">XML Processing Instruction Literal (Visual Basic)</span></span>

<span data-ttu-id="6f291-103">개체를 나타내는 리터럴입니다 <xref:System.Xml.Linq.XProcessingInstruction> .</span><span class="sxs-lookup"><span data-stu-id="6f291-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f291-104">구문</span><span class="sxs-lookup"><span data-stu-id="6f291-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="6f291-105">부분</span><span class="sxs-lookup"><span data-stu-id="6f291-105">Parts</span></span>  

 `<?`  
 <span data-ttu-id="6f291-106">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-106">Required.</span></span> <span data-ttu-id="6f291-107">XML 처리 명령 리터럴의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="6f291-108">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-108">Required.</span></span> <span data-ttu-id="6f291-109">처리 명령이 대상으로 하는 응용 프로그램을 나타내는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="6f291-110">"Xml" 또는 "XML"로 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="6f291-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-111">Optional.</span></span> <span data-ttu-id="6f291-112">에서 대상으로 하는 응용 프로그램이 `piName` XML 문서를 처리 하는 방법을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="6f291-113">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-113">Required.</span></span> <span data-ttu-id="6f291-114">처리 명령의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f291-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="6f291-115">Return Value</span></span>  

 <span data-ttu-id="6f291-116"><xref:System.Xml.Linq.XProcessingInstruction> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f291-117">설명</span><span class="sxs-lookup"><span data-stu-id="6f291-117">Remarks</span></span>  

 <span data-ttu-id="6f291-118">XML 처리 명령 리터럴은 응용 프로그램이 XML 문서를 처리 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="6f291-119">응용 프로그램이 XML 문서를 로드할 때 응용 프로그램은 XML 처리 명령을 확인 하 여 문서 처리 방법을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="6f291-120">응용 프로그램은 및의 의미를 해석 합니다 `piName` `piData` .</span><span class="sxs-lookup"><span data-stu-id="6f291-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="6f291-121">XML 문서 리터럴은 XML 처리 명령의 구문과 비슷한 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="6f291-122">자세한 내용은 [XML 문서 리터럴](xml-document-literal.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f291-122">For more information, see [XML Document Literal](xml-document-literal.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6f291-123">`piName`Xml 1.0 사양에서는 이러한 식별자를 예약 하기 때문에 요소는 문자열 "xml" 또는 "xml"로 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="6f291-124">XML 처리 명령 리터럴을 변수에 할당 하거나 XML 문서 리터럴에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6f291-125">XML 리터럴은 줄 연속 문자 없이 여러 줄에 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="6f291-126">이렇게 하면 XML 문서에서 콘텐츠를 복사 하 여 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="6f291-127">Visual Basic 컴파일러는 XML 처리 명령 리터럴을 생성자에 대 한 호출로 변환 합니다 <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> .</span><span class="sxs-lookup"><span data-stu-id="6f291-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f291-128">예제</span><span class="sxs-lookup"><span data-stu-id="6f291-128">Example</span></span>  

 <span data-ttu-id="6f291-129">다음 예에서는 XML 문서에 대 한 스타일 시트를 식별 하는 처리 명령을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6f291-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="6f291-130">참조</span><span class="sxs-lookup"><span data-stu-id="6f291-130">See also</span></span>

- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="6f291-131">XML 문서 리터럴</span><span class="sxs-lookup"><span data-stu-id="6f291-131">XML Document Literal</span></span>](xml-document-literal.md)
- [<span data-ttu-id="6f291-132">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="6f291-132">XML Literals</span></span>](index.md)
- [<span data-ttu-id="6f291-133">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="6f291-133">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
