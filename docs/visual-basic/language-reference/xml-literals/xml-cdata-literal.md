---
description: '자세한 정보: XML CDATA 리터럴 (Visual Basic)'
title: XML CDATA 리터럴
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: d0b419954acb5a9e8ae824dbac8234e2116d09b9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768755"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="802f9-103">XML CDATA 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="802f9-103">XML CDATA Literal (Visual Basic)</span></span>

<span data-ttu-id="802f9-104">개체를 나타내는 리터럴입니다 <xref:System.Xml.Linq.XCData> .</span><span class="sxs-lookup"><span data-stu-id="802f9-104">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="802f9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="802f9-105">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="802f9-106">부분</span><span class="sxs-lookup"><span data-stu-id="802f9-106">Parts</span></span>  

 `<![CDATA[`  
 <span data-ttu-id="802f9-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-107">Required.</span></span> <span data-ttu-id="802f9-108">XML CDATA 섹션의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-108">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="802f9-109">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-109">Required.</span></span> <span data-ttu-id="802f9-110">XML CDATA 섹션에 표시할 텍스트 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-110">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="802f9-111">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-111">Required.</span></span> <span data-ttu-id="802f9-112">섹션의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-112">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="802f9-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="802f9-113">Return Value</span></span>  

 <span data-ttu-id="802f9-114"><xref:System.Xml.Linq.XCData> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-114">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="802f9-115">설명</span><span class="sxs-lookup"><span data-stu-id="802f9-115">Remarks</span></span>  

 <span data-ttu-id="802f9-116">XML CDATA 섹션에는 포함 되어 있지만 구문 분석 되지 않은 원시 텍스트가 포함 된 XML로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-116">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="802f9-117">XML CDATA 섹션에는 모든 텍스트가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-117">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="802f9-118">여기에는 예약 된 XML 문자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-118">This includes reserved XML characters.</span></span> <span data-ttu-id="802f9-119">XML CDATA 섹션은 "]] >" 시퀀스로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-119">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="802f9-120">이는 다음 사항을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-120">This implies the following points:</span></span>  
  
- <span data-ttu-id="802f9-121">포함 된 식 구분 기호가 유효한 XML CDATA 콘텐츠 이므로 XML CDATA 리터럴에 포함 식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-121">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
- <span data-ttu-id="802f9-122">XML CDATA 섹션은 중첩 될 수 없습니다 `content` .에는 "]] >" 값을 사용할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-122">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="802f9-123">XML CDATA 리터럴을 변수에 할당 하거나 XML 요소 리터럴에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-123">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="802f9-124">XML 리터럴은 여러 줄에 걸쳐 있을 수 있지만 줄 연속 문자를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-124">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="802f9-125">이렇게 하면 XML 문서에서 콘텐츠를 복사 하 여 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="802f9-125">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="802f9-126">Visual Basic 컴파일러는 XML CDATA 리터럴을 생성자에 대 한 호출로 변환 합니다 <xref:System.Xml.Linq.XCData.%23ctor%2A> .</span><span class="sxs-lookup"><span data-stu-id="802f9-126">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="802f9-127">예제</span><span class="sxs-lookup"><span data-stu-id="802f9-127">Example</span></span>  

 <span data-ttu-id="802f9-128">다음 예제에서는 "리터럴 태그를 포함할 수 있습니다." 라는 텍스트가 포함 된 CDATA 섹션을 만듭니다 \<XML> .</span><span class="sxs-lookup"><span data-stu-id="802f9-128">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="802f9-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="802f9-129">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="802f9-130">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="802f9-130">XML Element Literal</span></span>](xml-element-literal.md)
- [<span data-ttu-id="802f9-131">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="802f9-131">XML Literals</span></span>](index.md)
- [<span data-ttu-id="802f9-132">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="802f9-132">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
