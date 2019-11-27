---
title: XML 트리 serialization
ms.date: 07/20/2015
ms.assetid: 2c340695-a726-4030-85be-6975d8a149cf
ms.openlocfilehash: 6b91078ff7f1b0410f97be9bc9ed3601f3ca0733
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351039"
---
# <a name="serializing-xml-trees-visual-basic"></a><span data-ttu-id="9464a-102">XML 트리 serialize (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9464a-102">Serializing XML Trees (Visual Basic)</span></span>
<span data-ttu-id="9464a-103">XML 트리를 serialize하는 것은 XML 트리에서 XML을 생성하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="9464a-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="9464a-104">파일, <xref:System.IO.TextWriter> 클래스의 구체적 구현 또는 <xref:System.Xml.XmlWriter>의 구체적 구현으로 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9464a-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="9464a-105">serialization의 다양한 측면을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9464a-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="9464a-106">예를 들어, serialize된 XML을 들여쓸지 여부와 XML 선언을 쓸지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9464a-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9464a-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="9464a-107">In This Section</span></span>  
  
|<span data-ttu-id="9464a-108">항목</span><span class="sxs-lookup"><span data-stu-id="9464a-108">Topic</span></span>|<span data-ttu-id="9464a-109">설명</span><span class="sxs-lookup"><span data-stu-id="9464a-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9464a-110">serialize할 때 공백 유지</span><span class="sxs-lookup"><span data-stu-id="9464a-110">Preserving White Space While Serializing</span></span>](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="9464a-111">XML 트리를 serialize할 때 공백 동작을 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9464a-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="9464a-112">XML 선언으로 serialize (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9464a-112">Serializing with an XML Declaration (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="9464a-113">XML 선언이 포함된 XML 트리를 serialize하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9464a-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="9464a-114">Files, TextWriters 및 XmlWriters로 serialization</span><span class="sxs-lookup"><span data-stu-id="9464a-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="9464a-115">문서를 <xref:System.IO.File>, <xref:System.IO.TextWriter> 또는 <xref:System.Xml.XmlWriter>로 serialize하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9464a-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="9464a-116">XmlReader로 serialize (XSLT 호출) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9464a-116">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="9464a-117">다른 모듈에서 XML 트리의 내용을 읽을 수 있도록 하는 <xref:System.Xml.XmlReader>를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9464a-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9464a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9464a-118">See also</span></span>

- [<span data-ttu-id="9464a-119">프로그래밍 가이드 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9464a-119">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
