---
description: '자세한 정보: Visual Basic에서 XML 만들기'
title: XML 만들기
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
ms.openlocfilehash: 9511253791720d1f45e00669b0abc41a45237f63
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100431648"
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="537b3-103">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="537b3-103">Creating XML in Visual Basic</span></span>

<span data-ttu-id="537b3-104">Visual Basic를 사용 하면 코드에서 직접 *XML 리터럴을* 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="537b3-104">Visual Basic enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="537b3-105">XML 리터럴 구문은 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체를 나타내며 xml 1.0 구문과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="537b3-105">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="537b3-106">이렇게 하면 코드의 구조가 최종 XML과 동일 하기 때문에 XML 요소, 문서 및 조각을 프로그래밍 방식으로 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="537b3-106">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="537b3-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="537b3-107">In This Section</span></span>  
  
|<span data-ttu-id="537b3-108">용어</span><span class="sxs-lookup"><span data-stu-id="537b3-108">Term</span></span>|<span data-ttu-id="537b3-109">정의</span><span class="sxs-lookup"><span data-stu-id="537b3-109">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="537b3-110">XML 리터럴 개요</span><span class="sxs-lookup"><span data-stu-id="537b3-110">XML Literals Overview</span></span>](xml-literals-overview.md)|<span data-ttu-id="537b3-111">XML 리터럴 및 이와 관련 된 방법에 대해 소개 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="537b3-111">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="537b3-112">XML의 포함 식</span><span class="sxs-lookup"><span data-stu-id="537b3-112">Embedded Expressions in XML</span></span>](embedded-expressions-in-xml.md)|<span data-ttu-id="537b3-113">XML 리터럴에 포함 된 식을 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="537b3-113">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="537b3-114">방법: XML 리터럴 만들기</span><span class="sxs-lookup"><span data-stu-id="537b3-114">How to: Create XML Literals</span></span>](how-to-create-xml-literals.md)|<span data-ttu-id="537b3-115">XML 리터럴을 사용 하 여 코드에서 XML 요소를 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="537b3-115">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="537b3-116">XML 리터럴의 공백</span><span class="sxs-lookup"><span data-stu-id="537b3-116">White Space in XML Literals</span></span>](white-space-in-xml-literals.md)|<span data-ttu-id="537b3-117">Visual Basic에서 XML 리터럴의 공백을 처리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="537b3-117">Describes how Visual Basic treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="537b3-118">XML 리터럴 및 XML 1.0 사양</span><span class="sxs-lookup"><span data-stu-id="537b3-118">XML Literals and the XML 1.0 Specification</span></span>](xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="537b3-119">Visual Basic의 XML 리터럴 구문이 XML 1.0 사양과 관련 된 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="537b3-119">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="537b3-120">방법: XML 리터럴에 식 포함</span><span class="sxs-lookup"><span data-stu-id="537b3-120">How to: Embed Expressions in XML Literals</span></span>](how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="537b3-121">XML 리터럴에 포함 식을 사용 하 여 런타임에 콘텐츠를 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="537b3-121">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="537b3-122">선언된 XML 요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="537b3-122">Names of Declared XML Elements and Attributes</span></span>](names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="537b3-123">XML 요소 및 특성의 이름을 지정 하기 위한 지침을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="537b3-123">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="537b3-124">추가 정보</span><span class="sxs-lookup"><span data-stu-id="537b3-124">See also</span></span>

- [<span data-ttu-id="537b3-125">XML</span><span class="sxs-lookup"><span data-stu-id="537b3-125">XML</span></span>](index.md)
