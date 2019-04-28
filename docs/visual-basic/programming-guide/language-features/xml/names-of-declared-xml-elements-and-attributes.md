---
title: 선언된 XML 요소 및 특성의 이름(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 2221f2677183cf360fa82a4d73a679a8b68927d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761704"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="5c0a1-102">선언된 XML 요소 및 특성의 이름(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c0a1-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="5c0a1-103">이 항목에서는 XML 요소 및 XML 리터럴의 특성 이름을 지정 하는 것에 대 한 Visual Basic 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-103">This topic provides Visual Basic guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="5c0a1-104">Xml 리터럴, 로컬 이름 또는 정규화 된 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="5c0a1-105">정규화 된 이름은 XML 네임 스페이스 접두사, 콜론 및 로컬 이름으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="5c0a1-106">XML 네임 스페이스 접두사에 대 한 자세한 내용은 참조 하세요. [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="5c0a1-107">규칙</span><span class="sxs-lookup"><span data-stu-id="5c0a1-107">Rules</span></span>  
 <span data-ttu-id="5c0a1-108">요소 또는 Visual Basic의 특성의 로컬 이름은 다음 규칙을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-108">A local name of an element or attribute in Visual Basic must adhere to the following rules.</span></span>  
  
- <span data-ttu-id="5c0a1-109">네임 스페이스를 사용 하 여 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-109">It can begin with a namespace.</span></span> <span data-ttu-id="5c0a1-110">알파벳 문자 또는 밑줄로 시작 해야 합니다 (`_`).</span><span class="sxs-lookup"><span data-stu-id="5c0a1-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="5c0a1-111">영문자, 10 진수 숫자, 밑줄, 마침표 (.) 및 하이픈만 포함 해야 합니다 (-).</span><span class="sxs-lookup"><span data-stu-id="5c0a1-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
- <span data-ttu-id="5c0a1-112">1,024 자 아니어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-112">It must not be more than 1,024 characters long.</span></span>  
  
- <span data-ttu-id="5c0a1-113">이름에 표시 되는 콜론 네임 스페이스 구분을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="5c0a1-114">따라서 특정 이름에 대 한 XML 네임 스페이스를 지정 하기 위해서만 콜론을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="5c0a1-115">또한 다음 지침을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-115">In addition, you should adhere to the following guideline.</span></span>  
  
- <span data-ttu-id="5c0a1-116">XML 1.0 사양에는 문자열의 대/소문자 변형 "xml"로 시작 하는 모든 이름을 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="5c0a1-117">따라서 이러한 요소에 대 한 이름 및 특성 이름을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="5c0a1-118">이름 길이 지침</span><span class="sxs-lookup"><span data-stu-id="5c0a1-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="5c0a1-119">실제 문제로 명확히 요소의 특성을 식별 하는 동안는 이름은 가능한 한 짧은 것 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="5c0a1-120">이 코드의 가독성을 향상 시키고 줄 길이 및 소스 파일 크기를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="5c0a1-121">그러나 프로그램 이름은 너무 짧아서는 설명 하지는 않습니다 적절 하 게 요소 또는 코드 방식을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="5c0a1-122">이 코드의 가독성을 위해 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-122">This is important for the readability of your code.</span></span> <span data-ttu-id="5c0a1-123">이해를 시도 하는 다른 사람에 게, 직접 살펴보면이 작성 한 후 오랫동안 적절 한 요소 이름을 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="5c0a1-124">이름에서 대/소문자 구분</span><span class="sxs-lookup"><span data-stu-id="5c0a1-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="5c0a1-125">XML 요소 이름은 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-125">XML element names are case sensitive.</span></span> <span data-ttu-id="5c0a1-126">이 Visual Basic 컴파일러는 알파벳 소문자만 다른 두 이름을 비교, 해석 다른 이름으로 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-126">This means that when the Visual Basic compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="5c0a1-127">예를 들어, 해석 `ABC` 및 `abc` 으로 요소를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="5c0a1-128">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="5c0a1-128">XML Namespaces</span></span>  
 <span data-ttu-id="5c0a1-129">XML 요소 리터럴를 만들 때 요소 이름에 대 한 XML 네임 스페이스 접두사를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="5c0a1-130">자세한 내용은 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5c0a1-130">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c0a1-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="5c0a1-131">See also</span></span>

- [<span data-ttu-id="5c0a1-132">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="5c0a1-132">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="5c0a1-133">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="5c0a1-133">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
