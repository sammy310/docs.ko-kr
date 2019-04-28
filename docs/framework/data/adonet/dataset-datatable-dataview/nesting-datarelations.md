---
title: DataRelation 중첩
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: 7975e17bd957a822bf3d60d487eb928cee84bd28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607325"
---
# <a name="nesting-datarelations"></a><span data-ttu-id="3d777-102">DataRelation 중첩</span><span class="sxs-lookup"><span data-stu-id="3d777-102">Nesting DataRelations</span></span>
<span data-ttu-id="3d777-103">데이터의 관계형 표현에서 각 테이블에는 열이나 열 집합을 사용하여 서로 연결시키는 행이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-103">In a relational representation of data, individual tables contain rows that are related to one another using a column or set of columns.</span></span> <span data-ttu-id="3d777-104">ADO.NET <xref:System.Data.DataSet>에서 각 테이블 사이의 관계는 <xref:System.Data.DataRelation>을 사용하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-104">In the ADO.NET <xref:System.Data.DataSet>, the relationship between tables is implemented using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="3d777-105">만들 때를 **DataRelation**, 열의 부모-자식 관계는 관계를 통해서만 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-105">When you create a **DataRelation**, the parent-child relationships of the columns are managed only through the relation.</span></span> <span data-ttu-id="3d777-106">테이블과 열은 별개의 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-106">The tables and columns are separate entities.</span></span> <span data-ttu-id="3d777-107">XML에서 제공하는 데이터의 계층적 표현에서 부모-자식 관계는 중첩된 자식 요소를 포함하는 부모 요소에 의해 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-107">In the hierarchical representation of data that XML provides, the parent-child relationships are represented by parent elements that contain nested child elements.</span></span>  
  
 <span data-ttu-id="3d777-108">자식 개체의 중첩을 용이 하 게 때를 **데이터 집합** 와 동기화 되는 <xref:System.Xml.XmlDataDocument> 사용 하 여 XML 데이터를 기록 하거나 **WriteXml**의 **DataRelation** 노출 된 **중첩** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-108">To facilitate the nesting of child objects when a **DataSet** is synchronized with an <xref:System.Xml.XmlDataDocument> or written as XML data using **WriteXml**, the **DataRelation** exposes a **Nested** property.</span></span> <span data-ttu-id="3d777-109">설정 합니다 **중첩** 의 속성을 **DataRelation** 에 **true** 자식 행을 XML 데이터로 작성 된 부모 열 내에서 중첩 된 관계의 발생 또는 동기화는 **XmlDataDocument**합니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-109">Setting the **Nested** property of a **DataRelation** to **true** causes the child rows of the relation to be nested within the parent column when written as XML data or synchronized with an **XmlDataDocument**.</span></span> <span data-ttu-id="3d777-110">**중첩** 의 속성을 **DataRelation** 은 **false**, 기본적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-110">The **Nested** property of the **DataRelation** is **false**, by default.</span></span>  
  
 <span data-ttu-id="3d777-111">예를 들어, 다음 사항을 고려 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-111">For example, consider the following **DataSet**.</span></span>  
  
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
  
 <span data-ttu-id="3d777-112">때문에 **중첩** 의 속성을 **DataRelation** 개체 설정 되지 않은 **true** 이 대 한 **데이터 집합**, 자식 개체 중첩 되지 않은 부모 요소에 있는 경우이 **데이터 집합** XML 데이터로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-112">Because the **Nested** property of the **DataRelation** object is not set to **true** for this **DataSet**, the child objects are not nested within the parent elements when this **DataSet** is represented as XML data.</span></span> <span data-ttu-id="3d777-113">XML 표현을 변형 된 **데이터 집합** 포함 된 관련 **데이터 집합**s 중첩 되지 않은 데이터 관계를 사용 하 여 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-113">Transforming the XML representation of a **DataSet** that contains related **DataSet**s with non-nested data relations can cause slow performance.</span></span> <span data-ttu-id="3d777-114">데이터 관계를 중첩하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-114">We recommend that you nest the data relations.</span></span> <span data-ttu-id="3d777-115">이 위해 설정 된 **중첩** 속성을 **true**합니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-115">To do this, set the **Nested** property to **true**.</span></span> <span data-ttu-id="3d777-116">그런 다음 XSLT 스타일시트에서 하향 계층 구조적인 XPath 쿼리 식을 사용하여 데이터를 찾고 변환하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-116">Then write code in the XSLT style sheet that uses top-down hierarchical XPath query expressions to locate and transform the data.</span></span>  
  
 <span data-ttu-id="3d777-117">다음 코드 예제에서는 호출의 결과로 **WriteXml** 에 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-117">The following code example shows the result from calling **WriteXml** on the **DataSet**.</span></span>  
  
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
  
 <span data-ttu-id="3d777-118">합니다 **고객** 요소와 **주문** 요소는 형제 요소로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-118">Note that the **Customers** element and the **Orders** elements are shown as sibling elements.</span></span> <span data-ttu-id="3d777-119">원한다 면를 **주문** 요소가 자신의 해당 부모 요소의 자식으로 표시 되는 데는 **중첩** 속성을 **DataRelation** 로설정해야**true** 다음을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-119">If you wanted the **Orders** elements to show up as children of their respective parent elements, the **Nested** property of the **DataRelation** would need to be set to **true** and you would add the following:</span></span>  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 <span data-ttu-id="3d777-120">다음 코드를 보여 줍니다 결과 출력은, 사용 하 여는 **주문** 자신의 해당 부모 요소 내에 중첩 된 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3d777-120">The following code shows what the resulting output would look like, with the **Orders** elements nested within their respective parent elements.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3d777-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="3d777-121">See also</span></span>

- [<span data-ttu-id="3d777-122">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="3d777-122">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="3d777-123">DataRelation 추가</span><span class="sxs-lookup"><span data-stu-id="3d777-123">Adding DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)
- [<span data-ttu-id="3d777-124">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="3d777-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="3d777-125">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="3d777-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
