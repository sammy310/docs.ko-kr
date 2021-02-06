---
description: '자세히 알아보기: XmlDataDocument를 사용 하 여 데이터 집합 동기화'
title: XmlDataDocument로 데이터 세트 동기화
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fbc96fa9-b5d1-4f97-b099-c89b0e14ce2c
ms.openlocfilehash: 5b5d95ef78746bb5b78146557a6ebd307895db13
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651550"
---
# <a name="synchronizing-a-dataset-with-an-xmldatadocument"></a><span data-ttu-id="a873b-103">XmlDataDocument로 데이터 세트 동기화</span><span class="sxs-lookup"><span data-stu-id="a873b-103">Synchronizing a DataSet with an XmlDataDocument</span></span>

<span data-ttu-id="a873b-104">이 단원에서는 <xref:System.Data.DataSet>와 동기화된 강력한 형식의 <xref:System.Xml.XmlDataDocument>을 사용하여 구매 주문을 처리하는 한 가지 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a873b-104">This section demonstrates one step in the processing of a purchase order, using a strongly typed <xref:System.Data.DataSet> synchronized with an <xref:System.Xml.XmlDataDocument>.</span></span> <span data-ttu-id="a873b-105">다음 예에서는 소스 XML 문서의 일부에만 일치 하는 최소화 된 스키마를 사용 하 여 **데이터 집합** 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a873b-105">The examples that follow create a **DataSet** with a minimized schema that matches only a portion of the source XML document.</span></span> <span data-ttu-id="a873b-106">이 예에서는 **XmlDataDocument** 를 사용 하 여 원본 xml 문서의 충실도를 유지 합니다 .이를 통해 **데이터 집합** 을 사용 하 여 xml 문서의 하위 집합을 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a873b-106">The examples use an **XmlDataDocument** to preserve the fidelity of the source XML document, enabling the **DataSet** to be used to expose a subset of the XML document.</span></span>  
  
 <span data-ttu-id="a873b-107">다음 XML 문서에는 고객 정보, 주문한 품목 및 배송 정보 등 구매 주문과 관련된 모든 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a873b-107">The following XML document contains all the information pertaining to a purchase order: customer information, items ordered, shipping information, and so on.</span></span>  
  
```xml  
<?xml version="1.0" standalone="yes"?>  
<PurchaseOrder>  
  <Customers>  
    <CustomerID>CHOPS</CustomerID>  
    <Orders>  
      <OrderID>10966</OrderID>  
      <OrderDetails>  
        <OrderID>10966</OrderID>  
        <ProductID>37</ProductID>  
        <UnitPrice>26</UnitPrice>  
        <Quantity>8</Quantity>  
        <Discount>0</Discount>  
      </OrderDetails>  
      <OrderDetails>  
        <OrderID>10966</OrderID>  
        <ProductID>56</ProductID>  
        <UnitPrice>38</UnitPrice>  
        <Quantity>12</Quantity>  
        <Discount>0.15</Discount>  
      </OrderDetails>  
      <OrderDetails>  
        <OrderID>10966</OrderID>  
        <ProductID>62</ProductID>  
        <UnitPrice>49.3</UnitPrice>  
        <Quantity>12</Quantity>  
        <Discount>0.15</Discount>  
      </OrderDetails>  
      <CustomerID>CHOPS</CustomerID>  
      <EmployeeID>4</EmployeeID>  
      <OrderDate>1998-03-20T00:00:00.0000000</OrderDate>  
      <RequiredDate>1998-04-17T00:00:00.0000000</RequiredDate>  
      <ShippedDate>1998-04-08T00:00:00.0000000</ShippedDate>  
      <ShipVia>1</ShipVia>  
      <Freight>27.19</Freight>  
      <ShipName>Chop-suey Chinese</ShipName>  
      <ShipAddress>Hauptstr. 31</ShipAddress>  
      <ShipCity>Bern</ShipCity>  
      <ShipPostalCode>3012</ShipPostalCode>  
      <ShipCountry>Switzerland</ShipCountry>  
    </Orders>  
    <CompanyName>Chop-suey Chinese</CompanyName>  
    <ContactName>Yang Wang</ContactName>  
    <ContactTitle>Owner</ContactTitle>  
    <Address>Hauptstr. 29</Address>  
    <City>Bern</City>  
    <PostalCode>3012</PostalCode>  
    <Country>Switzerland</Country>  
    <Phone>0452-076545</Phone>  
  </Customers>  
  <Shippers>  
    <ShipperID>1</ShipperID>  
    <CompanyName>Speedy Express</CompanyName>  
    <Phone>(503) 555-0100</Phone>  
  </Shippers>  
  <Shippers>  
    <ShipperID>2</ShipperID>  
    <CompanyName>United Package</CompanyName>  
    <Phone>(503) 555-0101</Phone>  
  </Shippers>  
  <Shippers>  
    <ShipperID>3</ShipperID>  
    <CompanyName>Federal Shipping</CompanyName>  
    <Phone>(503) 555-0102</Phone>  
  </Shippers>  
  <Products>  
    <ProductID>37</ProductID>  
    <ProductName>Gravad lax</ProductName>  
    <QuantityPerUnit>12 - 500 g pkgs.</QuantityPerUnit>  
    <UnitsInStock>11</UnitsInStock>  
    <UnitsOnOrder>50</UnitsOnOrder>  
    <ReorderLevel>25</ReorderLevel>  
  </Products>  
  <Products>  
    <ProductID>56</ProductID>  
    <ProductName>Gnocchi di nonna Alice</ProductName>  
    <QuantityPerUnit>24 - 250 g pkgs.</QuantityPerUnit>  
    <UnitsInStock>21</UnitsInStock>  
    <UnitsOnOrder>10</UnitsOnOrder>  
    <ReorderLevel>30</ReorderLevel>  
  </Products>  
  <Products>  
    <ProductID>62</ProductID>  
    <ProductName>Tarte au sucre</ProductName>  
    <QuantityPerUnit>48 pies</QuantityPerUnit>  
    <UnitsInStock>17</UnitsInStock>  
    <UnitsOnOrder>0</UnitsOnOrder>  
    <ReorderLevel>0</ReorderLevel>  
  </Products>  
</PurchaseOrder>  
```  
  
 <span data-ttu-id="a873b-108">앞의 XML 문서에 포함된 구매 주문 정보 처리 단계는 회사의 현재 재고품으로 주문을 채우기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a873b-108">One step in processing the purchase order information contained in the preceding XML document is for the order to be filled from the company's current inventory.</span></span> <span data-ttu-id="a873b-109">회사 창고에서 주문을 채우는 직원은 구매 주문의 전체 내용을 확인할 필요가 없으며, 해당 주문에 대한 제품 정보만 확인하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a873b-109">The employee responsible for filling the order from the company's warehouse does not need to see the entire contents of the purchase order; they only need to see the product information for the order.</span></span> <span data-ttu-id="a873b-110">XML 문서의 제품 정보만 표시 하려면 XSD (XML 스키마 정의 언어) 스키마로 작성 된 스키마를 사용 하 여 주문 된 제품 및 수량에 매핑되는 강력한 형식의 **데이터 집합** 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a873b-110">To expose only the product information from the XML document, create a strongly typed **DataSet** with a schema, written as XML Schema definition language (XSD) schema, that maps to the products and quantities ordered.</span></span> <span data-ttu-id="a873b-111">강력한 형식의 **데이터 집합** 개체에 대 한 자세한 내용은 [형식화 된 데이터](typed-datasets.md)집합을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a873b-111">For more information about strongly typed **DataSet** objects, see [Typed DataSets](typed-datasets.md).</span></span>  
  
 <span data-ttu-id="a873b-112">다음 코드에서는이 샘플에 대해 강력한 형식의 **데이터 집합** 을 생성 하는 스키마를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a873b-112">The following code shows the schema from which the strongly typed **DataSet** is generated for this sample.</span></span>  
  
```xml  
<?xml version="1.0" standalone="yes"?>  
<xs:schema id="OrderDetail" xmlns=""
                            xmlns:xs="http://www.w3.org/2001/XMLSchema"
                            xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"
                            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="OrderDetail" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetails" codegen:typedName="LineItem" codegen:typedPlural="LineItems">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" type="xs:int" minOccurs="0" codegen:typedName="OrderID"/>  
              <xs:element name="Quantity" type="xs:short" minOccurs="0" codegen:typedName="Quantity"/>  
              <xs:element name="ProductID" type="xs:int" minOccurs="0" codegen:typedName="ProductID"/>  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Products" codegen:typedName="Product" codegen:typedPlural="Products">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="ProductID" type="xs:int" minOccurs="0" codegen:typedName="ProductID"/>  
              <xs:element name="ProductName" type="xs:string" minOccurs="0" codegen:typedName="ProductName"/>  
              <xs:element name="QuantityPerUnit" type="xs:string" minOccurs="0" codegen:typedName="QuantityPerUnit"/>  
              <xs:element name="UnitsInStock" type="xs:short" minOccurs="0" codegen:typedName="UnitsInStock"/>  
              <xs:element name="UnitsOnOrder" type="xs:short" minOccurs="0" codegen:typedName="UnitsOnOrder"/>  
              <xs:element name="ReorderLevel" type="xs:short" minOccurs="0" codegen:typedName="ReorderLevel"/>  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
    <xs:unique name="Constraint1">  
      <xs:selector xpath=".//Products" />  
      <xs:field xpath="ProductID" />  
    </xs:unique>  
    <xs:keyref name="Relation1" refer="Constraint1" codegen:typedChildren="GetLineItems" codegen:typedParent="Product">  
      <xs:selector xpath=".//OrderDetails" />  
      <xs:field xpath="ProductID" />  
    </xs:keyref>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="a873b-113">원래 XML 문서의 **OrderDetails** 및 **Products** 요소에 있는 정보만 **데이터 집합** 에 대 한 스키마에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a873b-113">Notice that only information from the **OrderDetails** and **Products** elements of the original XML document are included in the schema for the **DataSet**.</span></span> <span data-ttu-id="a873b-114">**데이터 집합** 을 **XmlDataDocument** 와 동기화 하면 **데이터 집합** 에 포함 되지 않은 요소가 XML 문서와 함께 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a873b-114">Synchronizing the **DataSet** with an **XmlDataDocument** ensures that the elements not included in the **DataSet** will persist with the XML document.</span></span>  
  
 <span data-ttu-id="a873b-115">XML 스키마에서 생성 된 강력한 형식의 **데이터 집합** (XmlDataDocument **의 네임** 스페이스 포함)을 사용 하면 **데이터 집합** 을 원본 xml 문서에서 로드 된  와 동기화 하 여 원래 xml 문서의 일부를 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a873b-115">With the strongly typed **DataSet** generated from the XML Schema (with a namespace of **Northwind.FillOrder**), a portion of the original XML document can be exposed by synchronizing the **DataSet** with the **XmlDataDocument** loaded from the source XML document.</span></span> <span data-ttu-id="a873b-116">스키마에서 생성 된 **데이터 집합** 에는 구조는 포함 되지만 데이터는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a873b-116">Notice that the **DataSet** generated from the schema contains structure but no data.</span></span> <span data-ttu-id="a873b-117">**XmlDataDocument** 에 XML을 로드 하면 데이터가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="a873b-117">The data is filled in when you load the XML into the **XmlDataDocument**.</span></span> <span data-ttu-id="a873b-118">이미 데이터가 포함 된 데이터 **집합과** 동기화 된 **XmlDataDocument** 를 로드 하려고 하면 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a873b-118">If you attempt to load an **XmlDataDocument** that has been synchronized with a **DataSet** that already contains data, an exception will be thrown.</span></span>  
  
 <span data-ttu-id="a873b-119">**데이터 집합** (및 **XmlDataDocument**)을 업데이트 한 **후에는** 아래와 같이 **데이터 집합** 에서 무시 된 요소가 그대로 남아 있는 수정 된 XML 문서를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a873b-119">After the **DataSet** (and the **XmlDataDocument**) has been updated, the **XmlDataDocument** can then write out the modified XML document with the elements ignored by the **DataSet** still intact, as shown below.</span></span> <span data-ttu-id="a873b-120">구매 주문 시나리오에서 주문 항목을 채웠으면 수정된 XML 문서를 주문 과정의 다음 단계인 회사의 배송 부서로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a873b-120">In the purchase order scenario, after the order items have been filled, the modified XML document can then be passed on to the next step in the order process, perhaps to the company's shipping department.</span></span>  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Xml  
Imports Northwind.FillOrder  
  
Public class Sample  
  Public Shared Sub Main()  
  
    Dim orderDS As OrderDetail = New OrderDetail  
  
    Dim xmlDocument As XmlDataDocument = New XmlDataDocument(orderDS)
  
    xmlDocument.Load("Order.xml")  
  
    Dim orderItem As OrderDetail.LineItem  
    Dim product As OrderDetail.Product  
  
    For Each orderItem In orderDS.LineItems  
      product = orderItem.Product  
  
      ' Remove quantity from the current stock.  
      product.UnitsInStock = CType(product.UnitsInStock - orderItem.Quantity, Short)  
  
      ' If the remaining stock is less than the reorder level, order more.  
      If ((product.UnitsInStock + product.UnitsOnOrder) < product.ReorderLevel) Then  
        product.UnitsOnOrder = CType(product.UnitsOnOrder + product.ReorderLevel, Short)  
      End If  
    Next  
  
    xmlDocument.Save("Order_out.xml")  
  End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Xml;  
using Northwind.FillOrder;  
  
public class Sample  
{  
  public static void Main()  
  {  
    OrderDetail orderDS = new OrderDetail();
  
    XmlDataDocument xmlDocument = new XmlDataDocument(orderDS);
  
    xmlDocument.Load("Order.xml");  
  
    foreach (OrderDetail.LineItem orderItem in orderDS.LineItems)  
    {  
      OrderDetail.Product product = orderItem.Product;  
  
      // Remove quantity from the current stock.  
      product.UnitsInStock = (short)(product.UnitsInStock - orderItem.Quantity);  
  
      // If the remaining stock is less than the reorder level, order more.  
      if ((product.UnitsInStock + product.UnitsOnOrder) < product.ReorderLevel)  
        product.UnitsOnOrder = (short)(product.UnitsOnOrder + product.ReorderLevel);  
    }  
  
    xmlDocument.Save("Order_out.xml");  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a873b-121">참조</span><span class="sxs-lookup"><span data-stu-id="a873b-121">See also</span></span>

- [<span data-ttu-id="a873b-122">데이터 세트 및 XmlDataDocument 동기화</span><span class="sxs-lookup"><span data-stu-id="a873b-122">DataSet and XmlDataDocument Synchronization</span></span>](dataset-and-xmldatadocument-synchronization.md)
- [<span data-ttu-id="a873b-123">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="a873b-123">ADO.NET Overview</span></span>](../ado-net-overview.md)
