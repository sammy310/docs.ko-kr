---
title: LINQ to XML을 사용하여 XML 데이터 처리
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 059d6b9d-63f7-4011-9ba8-8406f0bbae7d
ms.openlocfilehash: 5afa9fc84b7f41023eceb5c0734b0667dc55514e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556501"
---
# <a name="process-xml-data-using-linq-to-xml"></a><span data-ttu-id="254a7-102">LINQ to XML을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="254a7-102">Process XML Data Using LINQ to XML</span></span>
<span data-ttu-id="254a7-103">LINQ to XML은 XML 데이터를 처리하기 위한 .NET Framework 버전 3.5의 새 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="254a7-103">LINQ to XML is the new model in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="254a7-104">LINQ to XML을 사용하여 XML 문서 쿼리, 수정, 작성, 저장, serialize 등 XML 데이터에 대한 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="254a7-104">LINQ to XML allows developers to do everything they would expect with XML data: querying, modifying, creating, saving, and serializing XML documents.</span></span> <span data-ttu-id="254a7-105">이 가운데 가장 실질적인 장점은 쿼리 및 작성 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="254a7-105">The real advantages lie in the query and creation capabilities.</span></span>  
  
 <span data-ttu-id="254a7-106">LINQ to XML의 쿼리는 XPath 또는 XQuery보다는 SQL에 유사한 구문을 사용하여 간결하고 표현이 다양합니다.</span><span class="sxs-lookup"><span data-stu-id="254a7-106">Queries in LINQ to XML are succinct and expressive, using syntax more similar to SQL than to XPath or XQuery.</span></span> <span data-ttu-id="254a7-107">쿼리 결과가 요소 또는 특성의 컬렉션으로 반환되어 XElement 개체의 매개 변수로 사용될 수 있으므로 XML 트리는 한 모형에서 다른 모형으로 쉽게 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="254a7-107">Because query results can be returned as collections of elements or attributes and can be used as parameters for XElement objects, XML trees can be easily transformed from one shape to another.</span></span>  
  
 <span data-ttu-id="254a7-108">LINQ to XML은 .NET Framework 버전 3.5의 LINQ(Language-Integrated Query) 기술을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="254a7-108">LINQ to XML leverages the language-integrated query (LINQ) technology in the .NET Framework version 3.5.</span></span> <span data-ttu-id="254a7-109">LINQ는 강력한 쿼리 기능을 제공하기 위해 C# 및 Visual Basic의 언어 구문을 확장하여 모든 데이터 저장소를 잠재적으로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="254a7-109">LINQ extends the language syntax of C# and Visual Basic to provide powerful query capabilities that can be extended to potentially any data store.</span></span>  
  
 <span data-ttu-id="254a7-110">용도에 대한 자세한 설명은 [LINQ to XML(C#)](../../linq/linq-xml-overview.md) 및 [LINQ to XML(Visual Basic)](../../linq/linq-xml-overview.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="254a7-110">For a detailed discussion of its use, see [LINQ to XML (C#)](../../linq/linq-xml-overview.md) and [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md).</span></span> <span data-ttu-id="254a7-111">LINQ 프레임워크 개요는 [LINQ(Language-Integrated Query) - C# ](../../../csharp/programming-guide/concepts/linq/index.md) 또는 [LINQ(Language-Integrated Query) - Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="254a7-111">For an overview of the LINQ framework, see [Language-Integrated Query (LINQ) - C#](../../../csharp/programming-guide/concepts/linq/index.md) or [Language-Integrated Query (LINQ) - Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="254a7-112">참조</span><span class="sxs-lookup"><span data-stu-id="254a7-112">See also</span></span>

- <xref:System.Xml.Linq>
- <xref:System.Linq>
- [<span data-ttu-id="254a7-113">LINQ to XML과 DOM 비교(C#)</span><span class="sxs-lookup"><span data-stu-id="254a7-113">LINQ to XML vs. DOM (C#)</span></span>](../../linq/linq-xml-vs-dom.md)
- [<span data-ttu-id="254a7-114">LINQ to XML과 DOM 비교(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="254a7-114">LINQ to XML vs. DOM (Visual Basic)</span></span>](../../linq/linq-xml-vs-dom.md)
- [<span data-ttu-id="254a7-115">LINQ to XML과 기타 XML 기술 비교(C#)</span><span class="sxs-lookup"><span data-stu-id="254a7-115">LINQ to XML vs. Other XML Technologies (C#)</span></span>](../../linq/linq-xml-vs-xml-technologies.md)
- [<span data-ttu-id="254a7-116">LINQ to XML과 기타 XML 기술 비교(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="254a7-116">LINQ to XML vs. Other XML Technologies (Visual Basic)</span></span>](../../linq/linq-xml-vs-xml-technologies.md)
