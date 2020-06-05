---
title: XML 구문 분석
ms.date: 07/20/2015
ms.assetid: 5bcbd7e2-d9f1-4c8f-80d6-39915fe17bd1
ms.openlocfilehash: 3517a0925e886dcd3d2d7860be606c4e44127cd6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406861"
---
# <a name="parsing-xml-visual-basic"></a><span data-ttu-id="ca2bc-102">XML 구문 분석 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca2bc-102">Parsing XML (Visual Basic)</span></span>
<span data-ttu-id="ca2bc-103">이 단원의 항목에서는 XML 문서의 구문을 분석하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2bc-103">The topics in this section describe how to parse XML documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ca2bc-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ca2bc-104">In This Section</span></span>  
  
|<span data-ttu-id="ca2bc-105">항목</span><span class="sxs-lookup"><span data-stu-id="ca2bc-105">Topic</span></span>|<span data-ttu-id="ca2bc-106">Description</span><span class="sxs-lookup"><span data-stu-id="ca2bc-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="ca2bc-107">방법: 문자열 구문 분석 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca2bc-107">How to: Parse a String (Visual Basic)</span></span>](how-to-parse-a-string.md)|<span data-ttu-id="ca2bc-108">문자열의 구문을 분석하여 XML 트리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca2bc-108">Shows how to parse a string to create an XML tree.</span></span>|  
|[<span data-ttu-id="ca2bc-109">방법: 파일에서 XML 로드 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca2bc-109">How to: Load XML from a File (Visual Basic)</span></span>](how-to-load-xml-from-a-file.md)|<span data-ttu-id="ca2bc-110"><xref:System.Xml.Linq.XElement.Load%2A> 메서드를 사용하여 URI에서 XML을 로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca2bc-110">Shows how to load XML from a URI using the <xref:System.Xml.Linq.XElement.Load%2A> method.</span></span>|  
|[<span data-ttu-id="ca2bc-111">XML을 로드 또는 구문 분석할 때 공백 유지</span><span class="sxs-lookup"><span data-stu-id="ca2bc-111">Preserving White Space while Loading or Parsing XML</span></span>](preserving-white-space-while-loading-or-parsing-xml.md)|<span data-ttu-id="ca2bc-112">XML 트리를 로드하는 동안 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]의 공백 동작을 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2bc-112">Describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] while loading XML trees.</span></span>|  
|[<span data-ttu-id="ca2bc-113">방법: 구문 분석 오류 Catch (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca2bc-113">How to: Catch Parsing Errors (Visual Basic)</span></span>](how-to-catch-parsing-errors.md)|<span data-ttu-id="ca2bc-114">잘못 구성되었거나 유효하지 않은 XML을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca2bc-114">Shows how to detect badly formed or invalid XML.</span></span>|  
|[<span data-ttu-id="ca2bc-115">방법: XmlReader에서 트리 만들기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca2bc-115">How to: Create a Tree from an XmlReader (Visual Basic)</span></span>](how-to-create-a-tree-from-an-xmlreader.md)|<span data-ttu-id="ca2bc-116"><xref:System.Xml.XmlReader>에서 XML 트리를 직접 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca2bc-116">Shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span>|  
|[<span data-ttu-id="ca2bc-117">방법: XmlReader에서 XML 조각 스트리밍 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca2bc-117">How to: Stream XML Fragments from an XmlReader (Visual Basic)</span></span>](how-to-stream-xml-fragments-from-an-xmlreader.md)|<span data-ttu-id="ca2bc-118"><xref:System.Xml.XmlReader>를 사용하여 XML 조각을 스트림하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca2bc-118">Shows how to stream XML fragments by using an <xref:System.Xml.XmlReader>.</span></span><br /><br /> <span data-ttu-id="ca2bc-119">예상할 수 없는 큰 크기의 XML 파일을 처리해야 하는 경우 전체 XML 트리를 메모리에 로드하는 것이 가능하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca2bc-119">When you have to process arbitrarily large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="ca2bc-120">이러한 경우 XML 조각을 스트림할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca2bc-120">Instead, you can stream XML fragments.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca2bc-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca2bc-121">See also</span></span>

- [<span data-ttu-id="ca2bc-122">XML 트리 만들기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca2bc-122">Creating XML Trees (Visual Basic)</span></span>](creating-xml-trees.md)
