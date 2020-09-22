---
title: XML CDATA 리터럴
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 4447ad6cf0fb251b0d2d1387c109b06d32f69cb8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866100"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="df40e-102">XML CDATA 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df40e-102">XML CDATA Literal (Visual Basic)</span></span>

<span data-ttu-id="df40e-103">개체를 나타내는 리터럴입니다 <xref:System.Xml.Linq.XCData> .</span><span class="sxs-lookup"><span data-stu-id="df40e-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df40e-104">구문</span><span class="sxs-lookup"><span data-stu-id="df40e-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="df40e-105">부분</span><span class="sxs-lookup"><span data-stu-id="df40e-105">Parts</span></span>  

 `<![CDATA[`  
 <span data-ttu-id="df40e-106">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-106">Required.</span></span> <span data-ttu-id="df40e-107">XML CDATA 섹션의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="df40e-108">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-108">Required.</span></span> <span data-ttu-id="df40e-109">XML CDATA 섹션에 표시할 텍스트 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="df40e-110">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-110">Required.</span></span> <span data-ttu-id="df40e-111">섹션의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df40e-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="df40e-112">Return Value</span></span>  

 <span data-ttu-id="df40e-113"><xref:System.Xml.Linq.XCData> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df40e-114">설명</span><span class="sxs-lookup"><span data-stu-id="df40e-114">Remarks</span></span>  

 <span data-ttu-id="df40e-115">XML CDATA 섹션에는 포함 되어 있지만 구문 분석 되지 않은 원시 텍스트가 포함 된 XML로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="df40e-116">XML CDATA 섹션에는 모든 텍스트가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="df40e-117">여기에는 예약 된 XML 문자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-117">This includes reserved XML characters.</span></span> <span data-ttu-id="df40e-118">XML CDATA 섹션은 "]] >" 시퀀스로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="df40e-119">이는 다음 사항을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-119">This implies the following points:</span></span>  
  
- <span data-ttu-id="df40e-120">포함 된 식 구분 기호가 유효한 XML CDATA 콘텐츠 이므로 XML CDATA 리터럴에 포함 식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
- <span data-ttu-id="df40e-121">XML CDATA 섹션은 중첩 될 수 없습니다 `content` .에는 "]] >" 값을 사용할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="df40e-122">XML CDATA 리터럴을 변수에 할당 하거나 XML 요소 리터럴에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df40e-123">XML 리터럴은 여러 줄에 걸쳐 있을 수 있지만 줄 연속 문자를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="df40e-124">이렇게 하면 XML 문서에서 콘텐츠를 복사 하 여 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df40e-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="df40e-125">Visual Basic 컴파일러는 XML CDATA 리터럴을 생성자에 대 한 호출로 변환 합니다 <xref:System.Xml.Linq.XCData.%23ctor%2A> .</span><span class="sxs-lookup"><span data-stu-id="df40e-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df40e-126">예제</span><span class="sxs-lookup"><span data-stu-id="df40e-126">Example</span></span>  

 <span data-ttu-id="df40e-127">다음 예제에서는 "리터럴 태그를 포함할 수 있습니다." 라는 텍스트가 포함 된 CDATA 섹션을 만듭니다 \<XML> .</span><span class="sxs-lookup"><span data-stu-id="df40e-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="df40e-128">참조</span><span class="sxs-lookup"><span data-stu-id="df40e-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="df40e-129">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="df40e-129">XML Element Literal</span></span>](xml-element-literal.md)
- [<span data-ttu-id="df40e-130">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="df40e-130">XML Literals</span></span>](index.md)
- [<span data-ttu-id="df40e-131">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="df40e-131">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
