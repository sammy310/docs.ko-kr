---
title: XML 선언으로 serialization
ms.date: 07/20/2015
ms.assetid: 8726f79e-2bb0-4ba0-969d-197cca591647
ms.openlocfilehash: 96c95b4c94290016684721a194ca31a836a49740
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350629"
---
# <a name="serializing-with-an-xml-declaration-visual-basic"></a><span data-ttu-id="724bc-102">XML 선언으로 serialize (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="724bc-102">Serializing with an XML Declaration (Visual Basic)</span></span>
<span data-ttu-id="724bc-103">이 항목에서는 serialization을 통해 XML 선언이 생성되는지 여부를 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="724bc-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="724bc-104">XML 선언 생성</span><span class="sxs-lookup"><span data-stu-id="724bc-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="724bc-105"><xref:System.IO.File> 메서드 또는 <xref:System.IO.TextWriter> 메서드를 사용하여 <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> 또는 <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>로 serialize하면 XML 선언이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="724bc-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> method generates an XML declaration.</span></span> <span data-ttu-id="724bc-106"><xref:System.Xml.XmlWriter>로 serialize하면 <xref:System.Xml.XmlWriterSettings> 개체에 지정된 작성기 설정에 따라 XML 선언이 생성되는지 여부가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="724bc-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="724bc-107">`ToString` 메서드를 사용하여 문자열로 serialize하는 경우 생성되는 XML에는 XML 선언이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="724bc-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="724bc-108">XML 선언으로 serialization</span><span class="sxs-lookup"><span data-stu-id="724bc-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="724bc-109">다음 예제에서는 <xref:System.Xml.Linq.XElement>를 만들고 문서를 파일에 저장한 다음 파일을 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="724bc-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child>child content</Child>  
                       </Root>  
root.Save("Root.xml")  
Dim str As String = File.ReadAllText("Root.xml")  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="724bc-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="724bc-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="724bc-111">XML 선언을 사용하지 않고 serialize</span><span class="sxs-lookup"><span data-stu-id="724bc-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="724bc-112">다음 예제에서는 <xref:System.Xml.Linq.XElement>를 <xref:System.Xml.XmlWriter>에 저장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="724bc-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```vb  
Dim sb As StringBuilder = New StringBuilder()  
Dim xws As XmlWriterSettings = New XmlWriterSettings()  
xws.OmitXmlDeclaration = True  
  
Using xw As XmlWriter = XmlWriter.Create(sb, xws)  
    Dim root = <Root>  
                   <Child>child content</Child>  
               </Root>  
    root.Save(xw)  
End Using  
Console.WriteLine(sb.ToString())  
```  
  
 <span data-ttu-id="724bc-113">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="724bc-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="724bc-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="724bc-114">See also</span></span>

- [<span data-ttu-id="724bc-115">XML 트리 serialize (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="724bc-115">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
