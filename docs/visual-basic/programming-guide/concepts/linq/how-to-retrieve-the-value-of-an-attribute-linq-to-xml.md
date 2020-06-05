---
title: '방법: 특성 값 검색(LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
ms.openlocfilehash: 48ad3c0ab079012793fd9eea89d52fc3a7b1698f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397806"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a><span data-ttu-id="bf6b5-102">방법: 특성 값 검색 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf6b5-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="bf6b5-103">이 항목에서는 특성의 값을 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf6b5-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="bf6b5-104">두 가지 주요 방법이 있습니다. <xref:System.Xml.Linq.XAttribute>를 원하는 형식으로 캐스팅할 수 있습니다. 그러면 명시적 변환 연산자가 요소나 특성의 내용을 지정된 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf6b5-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="bf6b5-105">또는 <xref:System.Xml.Linq.XAttribute.Value%2A> 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6b5-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="bf6b5-106">그러나 일반적으로 캐스팅이 더 나은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bf6b5-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="bf6b5-107">특성을 null 허용 값 형식으로 캐스팅하면 존재하지 않을 수도 있는 특성의 값을 검색하는 경우 코드를 더 간단하게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6b5-107">If you cast the attribute to a nullable value type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="bf6b5-108">이 기술에 대 한 예제 [는 방법: 요소 값 검색 (LINQ to XML) (Visual Basic)](how-to-retrieve-the-value-of-an-element-linq-to-xml.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf6b5-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)](how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf6b5-109">예제</span><span class="sxs-lookup"><span data-stu-id="bf6b5-109">Example</span></span>  
 <span data-ttu-id="bf6b5-110">Visual Basic에서는 통합 특성 속성을 사용하여 특성의 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6b5-110">In Visual Basic, you can use the integrated attribute property to retrieve the value of an attribute.</span></span>  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="bf6b5-111">이 예에서 생성되는 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6b5-111">This example produces the following output:</span></span>  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="bf6b5-112">예제</span><span class="sxs-lookup"><span data-stu-id="bf6b5-112">Example</span></span>  
 <span data-ttu-id="bf6b5-113">Visual Basic에서는 통합 특성 속성을 사용하여 특성의 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6b5-113">In Visual Basic, you can use the integrated attribute property to set the value of an attribute.</span></span> <span data-ttu-id="bf6b5-114">또한 통합 특성 속성을 사용하여 존재하지 않는 특성의 값을 설정하는 경우 특성이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="bf6b5-114">Further, if you use the integrated attribute property to set the value of an attribute that does not exist, the attribute will be created.</span></span>  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="bf6b5-115">이 예에서 생성되는 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6b5-115">This example produces the following output:</span></span>  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a><span data-ttu-id="bf6b5-116">예제</span><span class="sxs-lookup"><span data-stu-id="bf6b5-116">Example</span></span>  
 <span data-ttu-id="bf6b5-117">다음 예제에서는 특성이 네임스페이스에 있는 경우 특성의 값을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf6b5-117">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="bf6b5-118">자세한 내용은 [네임 스페이스 개요 (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf6b5-118">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root aw:Attr="abcde"/>  
        Dim str As String = root.@aw:Attr  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="bf6b5-119">이 예에서 생성되는 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6b5-119">This example produces the following output:</span></span>  
  
```console  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf6b5-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf6b5-120">See also</span></span>

- [<span data-ttu-id="bf6b5-121">LINQ to XML 축(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf6b5-121">LINQ to XML Axes (Visual Basic)</span></span>](linq-to-xml-axes.md)
