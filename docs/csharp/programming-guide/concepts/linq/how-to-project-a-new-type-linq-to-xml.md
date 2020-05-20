---
title: 새 형식을 프로젝션하는 방법(LINQ to XML)(C#)
ms.date: 07/20/2015
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: 5205a0c56651271dea0181ed96518c0e9d7f95f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168995"
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a><span data-ttu-id="37dc1-102">새 형식을 프로젝션하는 방법(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="37dc1-102">How to project a new type (LINQ to XML) (C#)</span></span>

<span data-ttu-id="37dc1-103">이 단원의 다른 예제에서는 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601>의 `string` 및 <xref:System.Collections.Generic.IEnumerable%601>의 `int`로 결과를 반환하는 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="37dc1-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="37dc1-104">이러한 결과 형식이 일반적이지만 모든 시나리오에 적합하지는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="37dc1-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="37dc1-105">대부분의 경우 다른 형식의 <xref:System.Collections.Generic.IEnumerable%601>을 반환하는 쿼리를 작성하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37dc1-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>

## <a name="example"></a><span data-ttu-id="37dc1-106">예제</span><span class="sxs-lookup"><span data-stu-id="37dc1-106">Example</span></span>

<span data-ttu-id="37dc1-107">이 예제에서는 `select` 절에서 개체를 인스턴스화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="37dc1-107">This example shows how to instantiate objects in the `select` clause.</span></span> <span data-ttu-id="37dc1-108">이 코드에서는 먼저 생성자를 사용하여 새 클래스를 정의한 다음 식이 새 클래스의 새 인스턴스이도록 `select` 문을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="37dc1-108">The code first defines a new class with a constructor, and then modifies the `select` statement so that the expression is a new instance of the new class.</span></span>

<span data-ttu-id="37dc1-109">이 예제에서는 XML 문서 [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37dc1-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>

```csharp
class NameQty
{
    public string name;
    public int qty;
    public NameQty(string n, int q)
    {
        name = n;
        qty = q;
    }
};

class Program {
    public static void Main()
    {
        XElement po = XElement.Load("PurchaseOrder.xml");
  
        IEnumerable<NameQty> nqList =
            from n in po.Descendants("Item")
            select new NameQty(
                    (string)n.Element("ProductName"),
                    (int)n.Element("Quantity")
                );
  
        foreach (NameQty n in nqList)
            Console.WriteLine(n.name + ":" + n.qty);
    }
}
```

<span data-ttu-id="37dc1-110">이 예제에서는 [단일 자식 요소를 검색하는 방법(LINQ to XML)(C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md) 항목에 도입된 <xref:System.Xml.Linq.XContainer.Element%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37dc1-110">This example uses the <xref:System.Xml.Linq.XContainer.Element%2A> method that was introduced in the topic [How to retrieve a single child element (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="37dc1-111">또한, 캐스트를 사용하여 <xref:System.Xml.Linq.XContainer.Element%2A> 메서드에서 반환하는 요소의 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="37dc1-111">It also uses casts to retrieve the values of the elements that are returned by the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>  

<span data-ttu-id="37dc1-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="37dc1-112">This example produces the following output:</span></span>

```output
Lawnmower:1
Baby Monitor:2
```
