---
description: '자세한 정보: DataRelations 중첩'
title: DataRelation 중첩
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: d998802a11fbb2bf414aa28b4beee95cac70a819
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651758"
---
# <a name="nesting-datarelations"></a><span data-ttu-id="7438a-103">DataRelation 중첩</span><span class="sxs-lookup"><span data-stu-id="7438a-103">Nesting DataRelations</span></span>

<span data-ttu-id="7438a-104">데이터의 관계형 표현에서 각 테이블에는 열이나 열 집합을 사용하여 서로 연결시키는 행이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-104">In a relational representation of data, individual tables contain rows that are related to one another using a column or set of columns.</span></span> <span data-ttu-id="7438a-105">ADO.NET <xref:System.Data.DataSet>에서 각 테이블 사이의 관계는 <xref:System.Data.DataRelation>을 사용하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-105">In the ADO.NET <xref:System.Data.DataSet>, the relationship between tables is implemented using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="7438a-106">**DataRelation** 을 만들 때 열의 부모-자식 관계는 관계를 통해서만 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-106">When you create a **DataRelation**, the parent-child relationships of the columns are managed only through the relation.</span></span> <span data-ttu-id="7438a-107">테이블과 열은 별개의 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-107">The tables and columns are separate entities.</span></span> <span data-ttu-id="7438a-108">XML에서 제공하는 데이터의 계층적 표현에서 부모-자식 관계는 중첩된 자식 요소를 포함하는 부모 요소에 의해 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-108">In the hierarchical representation of data that XML provides, the parent-child relationships are represented by parent elements that contain nested child elements.</span></span>  
  
 <span data-ttu-id="7438a-109">**데이터 집합이** 와 동기화 <xref:System.Xml.XmlDataDocument> 되거나 **WriteXml** 을 사용 하 여 XML 데이터로 작성 되는 경우 자식 개체의 중첩을 용이 하 게 하기 위해 **DataRelation** 은 **중첩** 된 속성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-109">To facilitate the nesting of child objects when a **DataSet** is synchronized with an <xref:System.Xml.XmlDataDocument> or written as XML data using **WriteXml**, the **DataRelation** exposes a **Nested** property.</span></span> <span data-ttu-id="7438a-110">**DataRelation** 의 **Nested** 속성을 **true** 로 설정 하면 XML 데이터로 작성 되거나 **XmlDataDocument** 와 동기화 될 때 관계의 자식 행이 부모 열에 중첩 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-110">Setting the **Nested** property of a **DataRelation** to **true** causes the child rows of the relation to be nested within the parent column when written as XML data or synchronized with an **XmlDataDocument**.</span></span> <span data-ttu-id="7438a-111">**DataRelation** 의 **Nested** 속성은 기본적으로 **false** 입니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-111">The **Nested** property of the **DataRelation** is **false**, by default.</span></span>  
  
 <span data-ttu-id="7438a-112">예를 들어 다음 **데이터 집합** 을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-112">For example, consider the following **DataSet**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection)  
  
connection.Open()  
  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
customerAdapter.Fill(dataSet, "Customers")  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
Dim customerOrders As DataRelation = dataSet.Relations.Add( _  
  "CustOrders", dataSet.Tables("Customers").Columns("CustomerID"), _  
  dataSet.Tables("Orders").Columns("CustomerID"))  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection);  
  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
customerAdapter.Fill(dataSet, "Customers");  
orderAdapter.Fill(dataSet, "Orders");  
  
connection.Close();  
  
DataRelation customerOrders = dataSet.Relations.Add(  
  "CustOrders", dataSet.Tables["Customers"].Columns["CustomerID"],  
  dataSet.Tables["Orders"].Columns["CustomerID"]);  
```  
  
 <span data-ttu-id="7438a-113">**DataRelation** 개체의 **Nested** **속성이이 데이터 집합에** 대해 **true** 로 설정 되어 있지 않기 때문에이 데이터 **집합이** XML 데이터로 표현 될 때 자식 개체는 부모 요소 내에 중첩 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-113">Because the **Nested** property of the **DataRelation** object is not set to **true** for this **DataSet**, the child objects are not nested within the parent elements when this **DataSet** is represented as XML data.</span></span> <span data-ttu-id="7438a-114">관련 데이터 **집합** 을 포함 하는 데이터 **집합** 의 XML 표현을 중첩 되지 않은 데이터 관계로 변환 하면 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-114">Transforming the XML representation of a **DataSet** that contains related **DataSet** s with non-nested data relations can cause slow performance.</span></span> <span data-ttu-id="7438a-115">데이터 관계를 중첩하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-115">We recommend that you nest the data relations.</span></span> <span data-ttu-id="7438a-116">이렇게 하려면 **Nested** 속성을 **true** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-116">To do this, set the **Nested** property to **true**.</span></span> <span data-ttu-id="7438a-117">그런 다음 XSLT 스타일시트에서 하향 계층 구조적인 XPath 쿼리 식을 사용하여 데이터를 찾고 변환하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-117">Then write code in the XSLT style sheet that uses top-down hierarchical XPath query expressions to locate and transform the data.</span></span>  
  
 <span data-ttu-id="7438a-118">다음 코드 예제에서는 **데이터 집합** 에 대해 **WriteXml** 를 호출한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-118">The following code example shows the result from calling **WriteXml** on the **DataSet**.</span></span>  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
  <Orders>  
    <OrderID>10643</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-08-25T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10692</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-10-03T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10308</OrderID>  
    <CustomerID>ANATR</CustomerID>  
    <OrderDate>1996-09-18T00:00:00</OrderDate>  
  </Orders>  
</CustomerOrders>  
```  
  
 <span data-ttu-id="7438a-119">**Customers** 요소와 **Orders** 요소는 형제 요소로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-119">Note that the **Customers** element and the **Orders** elements are shown as sibling elements.</span></span> <span data-ttu-id="7438a-120">**Orders** 요소가 해당 부모 요소의 자식으로 표시 되도록 하려면 **DataRelation** 의 **Nested** 속성을 **true** 로 설정 하 고 다음을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-120">If you wanted the **Orders** elements to show up as children of their respective parent elements, the **Nested** property of the **DataRelation** would need to be set to **true** and you would add the following:</span></span>  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 <span data-ttu-id="7438a-121">다음 코드에서는 결과 출력이 표시 되는 모양을 보여 줍니다. **Orders** 요소는 해당 부모 요소 내에 중첩 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7438a-121">The following code shows what the resulting output would look like, with the **Orders** elements nested within their respective parent elements.</span></span>  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <Orders>  
      <OrderID>10643</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-08-25T00:00:00</OrderDate>  
    </Orders>  
    <Orders>  
      <OrderID>10692</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-10-03T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <Orders>  
      <OrderID>10308</OrderID>  
      <CustomerID>ANATR</CustomerID>  
      <OrderDate>1996-09-18T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
</CustomerOrders>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7438a-122">참조</span><span class="sxs-lookup"><span data-stu-id="7438a-122">See also</span></span>

- [<span data-ttu-id="7438a-123">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="7438a-123">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="7438a-124">DataRelation 추가</span><span class="sxs-lookup"><span data-stu-id="7438a-124">Adding DataRelations</span></span>](adding-datarelations.md)
- [<span data-ttu-id="7438a-125">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="7438a-125">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="7438a-126">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="7438a-126">ADO.NET Overview</span></span>](../ado-net-overview.md)
