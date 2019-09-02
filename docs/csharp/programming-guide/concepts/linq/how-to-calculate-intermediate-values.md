---
title: '방법: 중간 값 계산(C#)'
ms.date: 07/20/2015
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: fe3f992e85b3fb508fced943e1428a4fb6ae2490
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205374"
---
# <a name="how-to-calculate-intermediate-values-c"></a><span data-ttu-id="19953-102">방법: 중간 값 계산(C#)</span><span class="sxs-lookup"><span data-stu-id="19953-102">How to: Calculate Intermediate Values (C#)</span></span>
<span data-ttu-id="19953-103">이 예제에서는 정렬, 필터링 및 선택에 사용할 수 있는 중간 값을 계산하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="19953-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19953-104">예</span><span class="sxs-lookup"><span data-stu-id="19953-104">Example</span></span>  
 <span data-ttu-id="19953-105">다음 예제에서는 `Let` 절을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="19953-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="19953-106">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 숫자 데이터(LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="19953-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> extensions =  
    from el in root.Elements("Data")  
    let extension = (decimal)el.Element("Quantity") * (decimal)el.Element("Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 <span data-ttu-id="19953-107">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="19953-107">This code produces the following output:</span></span>  
  
```output  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="19953-108">예</span><span class="sxs-lookup"><span data-stu-id="19953-108">Example</span></span>  
 <span data-ttu-id="19953-109">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="19953-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="19953-110">자세한 내용은 [네임스페이스 개요(LINQ to XML)(C#)](namespaces-overview-linq-to-xml.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19953-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="19953-111">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 네임스페이스의 숫자 데이터](./sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="19953-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<decimal> extensions =  
    from el in root.Elements(ad + "Data")  
    let extension = (decimal)el.Element(ad + "Quantity") * (decimal)el.Element(ad + "Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 <span data-ttu-id="19953-112">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="19953-112">This code produces the following output:</span></span>  
  
```output  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
