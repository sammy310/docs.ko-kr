---
title: XElement 요소를 포함하는 개체 그래프 serialization
ms.date: 07/20/2015
ms.assetid: c0cc5c92-5ca3-44b1-98dd-371601df721b
ms.openlocfilehash: caf594fc23eee15cc79cfad47e62a057518f62dd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349366"
---
# <a name="serializing-object-graphs-that-contain-xelement-objects-visual-basic"></a><span data-ttu-id="15719-102">XElement 개체를 포함 하는 개체 그래프 serialize (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15719-102">Serializing Object Graphs that Contain XElement Objects (Visual Basic)</span></span>
<span data-ttu-id="15719-103">이 항목에서는 <xref:System.Xml.Linq.XElement> 형식의 개체에 대한 참조가 포함된 개체 그래프를 serialize하는 기능에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="15719-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="15719-104">이러한 유형의 serialize를 용이하게 수행하기 위해 <xref:System.Xml.Linq.XElement>는 <xref:System.Xml.Serialization.IXmlSerializable> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="15719-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="15719-105"><xref:System.Xml.Linq.XElement> 클래스만 serialization을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="15719-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15719-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="15719-106">In This Section</span></span>  
  
|<span data-ttu-id="15719-107">항목</span><span class="sxs-lookup"><span data-stu-id="15719-107">Topic</span></span>|<span data-ttu-id="15719-108">설명</span><span class="sxs-lookup"><span data-stu-id="15719-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="15719-109">방법: XmlSerializer를 사용하여 serialize(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15719-109">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="15719-110"><xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15719-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="15719-111">방법: DataContractSerializer를 사용 하 여 Serialize (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15719-111">How to: Serialize Using DataContractSerializer (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="15719-112"><xref:System.Runtime.Serialization.DataContractSerializer>를 사용하여 serialize하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15719-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15719-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15719-113">See also</span></span>

- [<span data-ttu-id="15719-114">Visual Basic (Advanced LINQ to XML 프로그래밍)</span><span class="sxs-lookup"><span data-stu-id="15719-114">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
