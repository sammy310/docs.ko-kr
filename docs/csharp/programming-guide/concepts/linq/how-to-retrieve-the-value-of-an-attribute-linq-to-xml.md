---
title: 특성 값을 검색하는 방법(LINQ to XML)(C#)
ms.date: 07/20/2015
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
ms.openlocfilehash: 212ad3bb3097e7e2c76da8f165011b181f329d4c
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249196"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a><span data-ttu-id="29566-102">특성 값을 검색하는 방법(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="29566-102">How to retrieve the value of an attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="29566-103">이 항목에서는 특성의 값을 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29566-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="29566-104">두 가지 주요 방법이 있습니다. <xref:System.Xml.Linq.XAttribute>를 원하는 형식으로 캐스팅할 수 있습니다. 그러면 명시적 변환 연산자가 요소나 특성의 내용을 지정된 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="29566-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="29566-105">또는 <xref:System.Xml.Linq.XAttribute.Value%2A> 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29566-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="29566-106">그러나 일반적으로 캐스팅이 더 나은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="29566-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="29566-107">특성을 null 허용 값 형식으로 캐스팅하면 존재하지 않을 수도 있는 특성의 값을 검색하는 경우 코드를 더 간단하게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29566-107">If you cast the attribute to a nullable value type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="29566-108">이 방법의 예제는 [요소 값을 검색하는 방법(LINQ to XML)(C#)](./how-to-retrieve-the-value-of-an-element-linq-to-xml.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29566-108">For examples of this technique, see [How to retrieve the value of an element (LINQ to XML) (C#)](./how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="29566-109">예제</span><span class="sxs-lookup"><span data-stu-id="29566-109">Example</span></span>  
 <span data-ttu-id="29566-110">특성의 값을 검색하려면 <xref:System.Xml.Linq.XAttribute> 개체를 원하는 형식으로 캐스팅하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29566-110">To retrieve the value of an attribute, you just cast the <xref:System.Xml.Linq.XAttribute> object to your desired type.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
                    new XAttribute("Attr", "abcde")  
                );  
Console.WriteLine(root);  
string str = (string)root.Attribute("Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="29566-111">이 예에서 생성되는 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="29566-111">This example produces the following output:</span></span>  
  
```output  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="29566-112">예제</span><span class="sxs-lookup"><span data-stu-id="29566-112">Example</span></span>  
 <span data-ttu-id="29566-113">다음 예제에서는 특성이 네임스페이스에 있는 경우 특성의 값을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29566-113">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="29566-114">자세한 내용은 [네임스페이스 개요(LINQ to XML)(C#)](namespaces-overview-linq-to-xml.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29566-114">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="29566-115">이 예에서 생성되는 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="29566-115">This example produces the following output:</span></span>  
  
```output  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="29566-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="29566-116">See also</span></span>

- [<span data-ttu-id="29566-117">LINQ to XML 축(C#)</span><span class="sxs-lookup"><span data-stu-id="29566-117">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
