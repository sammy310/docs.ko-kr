---
title: XML 트리의 모양을 변환하는 방법(C#)
description: XML 트리의 모양을 변환하는 방법을 알아봅니다. XML 트리의 모양은 해당 요소 및 특성 이름과 해당 계층 구조 특성을 참조합니다.
ms.date: 07/20/2015
ms.assetid: 93c5d426-dea2-4709-a991-60204de42e8f
ms.openlocfilehash: 4fa3cc18f235d061ae1778c177c4ac9b626f4b71
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302648"
---
# <a name="how-to-transform-the-shape-of-an-xml-tree-c"></a><span data-ttu-id="d76a1-104">XML 트리의 모양을 변환하는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="d76a1-104">How to transform the shape of an XML tree (C#)</span></span>
<span data-ttu-id="d76a1-105">XML 문서의 *모양*은 요소 이름, 특성 이름 및 계층 구조의 특징을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d76a1-105">The *shape* of an XML document refers to its element names, attribute names, and the characteristics of its hierarchy.</span></span>  
  
 <span data-ttu-id="d76a1-106">XML 문서의 모양을 변경해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76a1-106">Sometimes you will have to change the shape of an XML document.</span></span> <span data-ttu-id="d76a1-107">예를 들어, 다른 요소 및 특성 이름이 필요한 다른 시스템에 기존 XML 문서를 보내야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76a1-107">For example, you might have to send an existing XML document to another system that requires different element and attribute names.</span></span> <span data-ttu-id="d76a1-108">문서를 살펴보면서 필요에 따라 요소를 삭제하고 요소의 이름을 바꿀 수 있지만 함수 생성을 사용하면 읽고 유지 관리하기가 더 쉬운 코드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d76a1-108">You could go through the document, deleting and renaming elements as required, but using functional construction results in more readable and maintainable code.</span></span> <span data-ttu-id="d76a1-109">함수 생성에 대한 자세한 내용은 [함수 생성(LINQ to XML)(C#)](./functional-construction-linq-to-xml.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d76a1-109">For more information about functional construction, see [Functional Construction (LINQ to XML) (C#)](./functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="d76a1-110">첫 번째 예제에서는 XML 문서의 구성을 변경하고</span><span class="sxs-lookup"><span data-stu-id="d76a1-110">The first example changes the organization of the XML document.</span></span> <span data-ttu-id="d76a1-111">트리의 한 위치에서 다른 위치로 복합 요소를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d76a1-111">It moves complex elements from one location in the tree to another.</span></span>  
  
 <span data-ttu-id="d76a1-112">이 항목의 두 번째 예제에서는 소스 문서와 모양이 다른 XML 문서를 만들고</span><span class="sxs-lookup"><span data-stu-id="d76a1-112">The second example in this topic creates an XML document with a different shape than the source document.</span></span> <span data-ttu-id="d76a1-113">요소 이름의 대/소문자를 변경한 다음 일부 요소의 이름을 바꾸고 소스 트리의 일부 요소를 변환된 트리 외부에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="d76a1-113">It changes the casing of the element names, renames some elements, and leaves some elements from the source tree out of the transformed tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d76a1-114">예제</span><span class="sxs-lookup"><span data-stu-id="d76a1-114">Example</span></span>  
 <span data-ttu-id="d76a1-115">다음 코드에서는 포함된 쿼리 식을 사용하여 XML 파일의 모양을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d76a1-115">The following code changes the shape of an XML file using embedded query expressions.</span></span>  
  
 <span data-ttu-id="d76a1-116">이 예제의 소스 XML 문서에는 `Customers` 요소 아래에 모든 고객이 포함된 `Root` 요소가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76a1-116">The source XML document in this example contains a `Customers` element under the `Root` element that contains all customers.</span></span> <span data-ttu-id="d76a1-117">또한 `Orders` 요소 아래에 모든 주문이 포함된 `Root` 요소도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76a1-117">It also contains an `Orders` element under the `Root` element that contains all orders.</span></span> <span data-ttu-id="d76a1-118">이 예제에서는 각 고객의 주문이 `Orders` 요소에 있는 `Customer` 요소에 포함되어 있는 새 XML 트리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d76a1-118">This example creates a new XML tree in which the orders for each customer are contained in an `Orders` element within the `Customer` element.</span></span> <span data-ttu-id="d76a1-119">원래 문서에도 `CustomerID` 요소에 `Order` 요소가 포함되어 있습니다. 이 요소는 모양이 다시 변경된 문서에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d76a1-119">The original document also contains a `CustomerID` element in the `Order` element; this element will be removed from the re-shaped document.</span></span>  
  
 <span data-ttu-id="d76a1-120">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: Customers 및 Orders(LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="d76a1-120">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XElement co = XElement.Load("CustomersOrders.xml");  
XElement newCustOrd =  
    new XElement("Root",  
        from cust in co.Element("Customers").Elements("Customer")  
        select new XElement("Customer",  
            cust.Attributes(),  
            cust.Elements(),  
            new XElement("Orders",  
                from ord in co.Element("Orders").Elements("Order")  
                where (string)ord.Element("CustomerID") == (string)cust.Attribute("CustomerID")  
                select new XElement("Order",  
                    ord.Attributes(),  
                    ord.Element("EmployeeID"),  
                    ord.Element("OrderDate"),  
                    ord.Element("RequiredDate"),  
                    ord.Element("ShipInfo")  
                )  
            )  
        )  
    );  
Console.WriteLine(newCustOrd);  
```  
  
 <span data-ttu-id="d76a1-121">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d76a1-121">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Customer CustomerID="GREAL">  
    <CompanyName>Great Lakes Food Market</CompanyName>  
    <ContactName>Howard Snyder</ContactName>  
    <ContactTitle>Marketing Manager</ContactTitle>  
    <Phone>(503) 555-7555</Phone>  
    <FullAddress>  
      <Address>2732 Baker Blvd.</Address>  
      <City>Eugene</City>  
      <Region>OR</Region>  
      <PostalCode>97403</PostalCode>  
      <Country>USA</Country>  
    </FullAddress>  
    <Orders />  
  </Customer>  
  <Customer CustomerID="HUNGC">  
    <CompanyName>Hungry Coyote Import Store</CompanyName>  
    <ContactName>Yoshi Latimer</ContactName>  
    <ContactTitle>Sales Representative</ContactTitle>  
    <Phone>(503) 555-6874</Phone>  
    <Fax>(503) 555-2376</Fax>  
    <FullAddress>  
      <Address>City Center Plaza 516 Main St.</Address>  
      <City>Elgin</City>  
      <Region>OR</Region>  
      <PostalCode>97827</PostalCode>  
      <Country>USA</Country>  
    </FullAddress>  
    <Orders />  
  </Customer>  
  . . .  
```  
  
## <a name="example"></a><span data-ttu-id="d76a1-122">예제</span><span class="sxs-lookup"><span data-stu-id="d76a1-122">Example</span></span>  
 <span data-ttu-id="d76a1-123">이 예제에서는 일부 요소의 이름을 바꾸고 일부 특성을 요소로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d76a1-123">This example renames some elements and converts some attributes to elements.</span></span>  
  
 <span data-ttu-id="d76a1-124">코드에서는 `ConvertAddress` 개체의 목록을 반환하는 <xref:System.Xml.Linq.XElement>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d76a1-124">The code calls `ConvertAddress`, which returns a list of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="d76a1-125">메서드의 인수는 `Address` 특성의 값이 `Type`인 `"Shipping"` 복합 요소를 확인하는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="d76a1-125">The argument to the method is a query that determines the `Address` complex element where the `Type` attribute has a value of `"Shipping"`.</span></span>  
  
 <span data-ttu-id="d76a1-126">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="d76a1-126">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
static IEnumerable<XElement> ConvertAddress(XElement add)  
{  
    List<XElement> fragment = new List<XElement>() {  
        new XElement("NAME", (string)add.Element("Name")),  
        new XElement("STREET", (string)add.Element("Street")),  
        new XElement("CITY", (string)add.Element("City")),  
        new XElement("ST", (string)add.Element("State")),  
        new XElement("POSTALCODE", (string)add.Element("Zip")),  
        new XElement("COUNTRY", (string)add.Element("Country"))  
    };  
    return fragment;  
}  
  
static void Main(string[] args)  
{  
    XElement po = XElement.Load("PurchaseOrder.xml");  
    XElement newPo = new XElement("PO",  
        new XElement("ID", (string)po.Attribute("PurchaseOrderNumber")),  
        new XElement("DATE", (DateTime)po.Attribute("OrderDate")),  
        ConvertAddress(  
            (from el in po.Elements("Address")  
            where (string)el.Attribute("Type") == "Shipping"  
            select el)  
            .First()  
        )  
    );  
    Console.WriteLine(newPo);  
}  
```  
  
 <span data-ttu-id="d76a1-127">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d76a1-127">This code produces the following output:</span></span>  
  
```xml  
<PO>  
  <ID>99503</ID>  
  <DATE>1999-10-20T00:00:00</DATE>  
  <NAME>Ellen Adams</NAME>  
  <STREET>123 Maple Street</STREET>  
  <CITY>Mill Valley</CITY>  
  <ST>CA</ST>  
  <POSTALCODE>10999</POSTALCODE>  
  <COUNTRY>USA</COUNTRY>  
</PO>  
```  
