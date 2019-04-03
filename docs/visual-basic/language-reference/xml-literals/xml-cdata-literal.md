---
title: XML CDATA 리터럴(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: ee269ca5cf9635fec35165d1ea65d6a6483cadef
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828602"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="84b63-102">XML CDATA 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84b63-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="84b63-103">리터럴 나타내는 <xref:System.Xml.Linq.XCData> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84b63-104">구문</span><span class="sxs-lookup"><span data-stu-id="84b63-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="84b63-105">요소</span><span class="sxs-lookup"><span data-stu-id="84b63-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="84b63-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="84b63-106">Required.</span></span> <span data-ttu-id="84b63-107">XML CDATA 섹션의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="84b63-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="84b63-108">Required.</span></span> <span data-ttu-id="84b63-109">XML CDATA 섹션에 표시할 텍스트 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="84b63-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="84b63-110">Required.</span></span> <span data-ttu-id="84b63-111">섹션의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84b63-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="84b63-112">Return Value</span></span>  
 <span data-ttu-id="84b63-113"><xref:System.Xml.Linq.XCData> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84b63-114">설명</span><span class="sxs-lookup"><span data-stu-id="84b63-114">Remarks</span></span>  
 <span data-ttu-id="84b63-115">XML CDATA 섹션에는 포함 하지만 구문 분석 되지 포함 하는 XML을 사용 하 여 해야 하는 원시 텍스트를 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="84b63-116">XML CDATA 섹션 모든 텍스트를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="84b63-117">예약 된 XML 문자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-117">This includes reserved XML characters.</span></span> <span data-ttu-id="84b63-118">XML CDATA 섹션 종료 시퀀스를 사용 하 여 "]] >"입니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="84b63-119">이 다음 사항을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-119">This implies the following points:</span></span>  
  
-   <span data-ttu-id="84b63-120">포함된 식 구분 기호는 유효한 XML CDATA 내용 때문에 XML CDATA 리터럴 포함된 식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
-   <span data-ttu-id="84b63-121">XML CDATA 섹션 중첩 될 수 없으므로 있으므로 `content` 값을 포함할 수 없습니다 "]] >"입니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="84b63-122">XML 주석 리터럴에서 변수에 할당할 수도 있고 XML 요소 리터럴에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84b63-123">XML 리터럴을 여러 줄으로 나누어 입력할 수 있지만 줄 연속 문자를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="84b63-124">이 옵션을 사용 하면 XML 문서에서 콘텐츠를 복사 하 고 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="84b63-125">Visual Basic 컴파일러를 호출 하는 XML CDATA 리터럴 변환 된 <xref:System.Xml.Linq.XCData.%23ctor%2A> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84b63-126">예제</span><span class="sxs-lookup"><span data-stu-id="84b63-126">Example</span></span>  
 <span data-ttu-id="84b63-127">다음 예제에서는 텍스트를 포함 하는 CDATA 섹션 "리터럴 포함 될 수 있습니다 \<XML > 태그"입니다.</span><span class="sxs-lookup"><span data-stu-id="84b63-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="84b63-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="84b63-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="84b63-129">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="84b63-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="84b63-130">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="84b63-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="84b63-131">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="84b63-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
