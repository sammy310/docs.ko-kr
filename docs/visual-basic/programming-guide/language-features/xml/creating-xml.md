---
title: Visual Basic에서 XML 만들기
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
ms.openlocfilehash: d847f589bc47f8ab3d6691666bbd879e795db0c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813043"
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="827d0-102">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="827d0-102">Creating XML in Visual Basic</span></span>
<span data-ttu-id="827d0-103">Visual Basic을 사용 하면 사용할 수 있습니다 *XML 리터럴을* 코드에서 직접.</span><span class="sxs-lookup"><span data-stu-id="827d0-103">Visual Basic enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="827d0-104">XML 리터럴 구문을 나타내는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체 및 해당 하는 XML 1.0 구문과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="827d0-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="827d0-105">이렇게 하면 쉽게 코드에 동일한 최종 XML 구조 때문에 XML 요소, 문서 및 조각을 프로그래밍 방식으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827d0-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="827d0-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="827d0-106">In This Section</span></span>  
  
|<span data-ttu-id="827d0-107">용어</span><span class="sxs-lookup"><span data-stu-id="827d0-107">Term</span></span>|<span data-ttu-id="827d0-108">정의</span><span class="sxs-lookup"><span data-stu-id="827d0-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="827d0-109">XML 리터럴 개요</span><span class="sxs-lookup"><span data-stu-id="827d0-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="827d0-110">XML 리터럴 및 관계를 소개 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="827d0-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="827d0-111">XML의 포함 식</span><span class="sxs-lookup"><span data-stu-id="827d0-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="827d0-112">XML 리터럴의 포함된 식을 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="827d0-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="827d0-113">방법: XML 리터럴 만들기</span><span class="sxs-lookup"><span data-stu-id="827d0-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="827d0-114">XML 리터럴을 사용 하 여 코드에서 XML 요소를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="827d0-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="827d0-115">XML 리터럴의 공백</span><span class="sxs-lookup"><span data-stu-id="827d0-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="827d0-116">Visual Basic XML 리터럴의 공백 문자를 처리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="827d0-116">Describes how Visual Basic treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="827d0-117">XML 리터럴 및 XML 1.0 사양</span><span class="sxs-lookup"><span data-stu-id="827d0-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="827d0-118">Visual Basic의 XML 리터럴 구문을 XML 1.0 사양에 연결 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="827d0-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="827d0-119">방법: XML 리터럴에 식 포함</span><span class="sxs-lookup"><span data-stu-id="827d0-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="827d0-120">XML 리터럴의 포함 된 식을 사용 하 여 런타임에 콘텐츠를 작성 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="827d0-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="827d0-121">선언된 XML 요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="827d0-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="827d0-122">XML 요소 및 특성 이름을 지정 하는 것에 대 한 지침을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="827d0-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="827d0-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="827d0-123">See also</span></span>

- [<span data-ttu-id="827d0-124">XML</span><span class="sxs-lookup"><span data-stu-id="827d0-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
