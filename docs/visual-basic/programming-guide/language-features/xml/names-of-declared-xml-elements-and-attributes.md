---
title: 선언된 XML 요소 및 특성의 이름
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 12fbd1f4332391b1acdcf12e101d82627ebbeaff
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335997"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="61ede-102">선언된 XML 요소 및 특성의 이름(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61ede-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="61ede-103">이 항목에서는 xml 리터럴의 XML 요소와 특성 이름을 지정 하는 Visual Basic 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-103">This topic provides Visual Basic guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="61ede-104">XML 리터럴에서 로컬 이름 또는 정규화 된 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="61ede-105">정규화 된 이름은 XML 네임 스페이스 접두사, 콜론 및 로컬 이름으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="61ede-106">XML 네임 스페이스 접두사에 대 한 자세한 내용은 [Xml 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61ede-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="61ede-107">규칙</span><span class="sxs-lookup"><span data-stu-id="61ede-107">Rules</span></span>  
 <span data-ttu-id="61ede-108">Visual Basic에 있는 요소 또는 특성의 로컬 이름은 다음 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-108">A local name of an element or attribute in Visual Basic must adhere to the following rules.</span></span>  
  
- <span data-ttu-id="61ede-109">네임 스페이스로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-109">It can begin with a namespace.</span></span> <span data-ttu-id="61ede-110">알파벳 문자 또는 밑줄 (`_`)로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="61ede-111">알파벳 문자, 10 진수 숫자, 밑줄, 마침표 (.) 및 하이픈 (-)만 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
- <span data-ttu-id="61ede-112">길이는 1024 자이 하 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-112">It must not be more than 1,024 characters long.</span></span>  
  
- <span data-ttu-id="61ede-113">이름에 표시 되는 콜론은 네임 스페이스 경계를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="61ede-114">따라서 콜론만 사용 하 여 특정 이름에 대 한 XML 네임 스페이스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="61ede-115">또한 다음 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-115">In addition, you should adhere to the following guideline.</span></span>  
  
- <span data-ttu-id="61ede-116">XML 1.0 사양은 대문자 변형의 문자열 "xml"로 시작 하는 모든 이름을 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="61ede-117">따라서 요소 및 특성 이름에는 이러한 이름을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="61ede-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="61ede-118">이름 길이 지침</span><span class="sxs-lookup"><span data-stu-id="61ede-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="61ede-119">실제로는 요소의 특성을 명확 하 게 식별 하면서 가능한 한 짧은 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="61ede-120">이렇게 하면 코드의 가독성을 높이고 줄 길이와 소스 파일 크기를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="61ede-121">그러나 요소 또는 코드에서 요소를 사용 하는 방법을 적절 하 게 설명 하지 않는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="61ede-122">이는 코드의 가독성을 높이기 위해 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-122">This is important for the readability of your code.</span></span> <span data-ttu-id="61ede-123">다른 사용자가이를 이해 하려고 하거나 사용자가 작성 한 후 오랜 시간을 확인 하는 경우 적절 한 요소 이름을 통해 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="61ede-124">이름에서 대/소문자 구분</span><span class="sxs-lookup"><span data-stu-id="61ede-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="61ede-125">XML 요소 이름은 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-125">XML element names are case sensitive.</span></span> <span data-ttu-id="61ede-126">즉, Visual Basic 컴파일러는 알파벳 대/소문자만 다른 두 이름을 비교할 때 다른 이름으로 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-126">This means that when the Visual Basic compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="61ede-127">예를 들어 `ABC`를 해석 하 고 개별 요소를 참조 하는 `abc` 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="61ede-128">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="61ede-128">XML Namespaces</span></span>  
 <span data-ttu-id="61ede-129">XML 요소 리터럴을 만들 때 요소 이름에 대 한 XML 네임 스페이스 접두사를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ede-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="61ede-130">자세한 내용은 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61ede-130">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61ede-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61ede-131">See also</span></span>

- [<span data-ttu-id="61ede-132">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="61ede-132">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="61ede-133">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="61ede-133">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
