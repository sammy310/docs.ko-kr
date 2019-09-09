---
title: '방법: 특정 자식 요소로 요소 찾기(C#)'
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: f007bddcbecc1cb938d05c7d444d29b6047749e8
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253749"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="9b9a7-102">방법: 특정 자식 요소로 요소 찾기(C#)</span><span class="sxs-lookup"><span data-stu-id="9b9a7-102">How to: Find an Element with a Specific Child Element (C#)</span></span>
<span data-ttu-id="9b9a7-103">이 항목에서는 지정된 값을 가진 자식 요소가 포함된 특정 요소를 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a7-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b9a7-104">예</span><span class="sxs-lookup"><span data-stu-id="9b9a7-104">Example</span></span>  
 <span data-ttu-id="9b9a7-105">이 예제에서는 값이 "Examp2.EXE"인 `Test` 자식 요소가 포함된 `CommandLine` 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a7-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="9b9a7-106">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 테스트 구성(LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9b9a7-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="9b9a7-107">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a7-107">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="9b9a7-108">예</span><span class="sxs-lookup"><span data-stu-id="9b9a7-108">Example</span></span>  
 <span data-ttu-id="9b9a7-109">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a7-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="9b9a7-110">자세한 내용은 [네임스페이스 개요(LINQ to XML)(C#)](namespaces-overview-linq-to-xml.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b9a7-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="9b9a7-111">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 네임스페이스에서 테스트 구성](./sample-xml-file-test-configuration-in-a-namespace1.md).</span><span class="sxs-lookup"><span data-stu-id="9b9a7-111">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](./sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfigInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<XElement> tests =  
    from el in root.Elements(ad + "Test")  
    where (string)el.Element(ad + "CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="9b9a7-112">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a7-112">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b9a7-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b9a7-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="9b9a7-114">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="9b9a7-114">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="9b9a7-115">프로젝션 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="9b9a7-115">Projection Operations (C#)</span></span>](./projection-operations.md)
