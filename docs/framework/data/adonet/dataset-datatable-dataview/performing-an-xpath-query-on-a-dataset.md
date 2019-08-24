---
title: 데이터 세트에서 XPath 쿼리 수행
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: 29d1e5ae494b2fff4e13886159bb937041152382
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607902"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a><span data-ttu-id="ff48a-102">데이터 세트에서 XPath 쿼리 수행</span><span class="sxs-lookup"><span data-stu-id="ff48a-102">Performing an XPath Query on a DataSet</span></span>
<span data-ttu-id="ff48a-103">동기화 관계 <xref:System.Data.DataSet> 및 <xref:System.Xml.XmlDataDocument> XML을 활용할 수 있습니다와 같은 서비스 XML Path Language (XPath) 쿼리를 액세스 하는 합니다 **XmlDataDocument** 특정 기능을 수행할 수 있습니다 액세스할 때 보다 더 편리 하 게 합니다 **데이터 집합** 직접.</span><span class="sxs-lookup"><span data-stu-id="ff48a-103">The relationship between a synchronized <xref:System.Data.DataSet> and <xref:System.Xml.XmlDataDocument> allows you to make use of XML services, such as the XML Path Language (XPath) query, that access the **XmlDataDocument** and can perform certain functionality more conveniently than accessing the **DataSet** directly.</span></span> <span data-ttu-id="ff48a-104">예를 들어, 사용 하는 대신를 **선택** 메서드를 <xref:System.Data.DataTable> 다른 테이블에 관계를 탐색 하는 **데이터 집합**에서 XPath 쿼리를 수행할 수 있습니다는 **XmlDataDocument**  와 동기화 된 합니다 **데이터 집합**, 형태로 XML 요소의 목록을 가져오려면는 <xref:System.Xml.XmlNodeList>합니다.</span><span class="sxs-lookup"><span data-stu-id="ff48a-104">For example, rather than using the **Select** method of a <xref:System.Data.DataTable> to navigate relationships to other tables in a **DataSet**, you can perform an XPath query on an **XmlDataDocument** that is synchronized with the **DataSet**, to get a list of XML elements in the form of an <xref:System.Xml.XmlNodeList>.</span></span> <span data-ttu-id="ff48a-105">노드를 **XmlNodeList**로 캐스팅 <xref:System.Xml.XmlElement> 노드를 전달할 수 있습니다 합니다 **GetRowFromElement** 메서드의 **XmlDataDocument**일치 하는 반환 하려는 경우 <xref:System.Data.DataRow> 동기화 된 테이블의 행에 대 한 참조가 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="ff48a-105">The nodes in the **XmlNodeList**, cast as <xref:System.Xml.XmlElement> nodes, can then be passed to the **GetRowFromElement** method of the **XmlDataDocument**, to return matching <xref:System.Data.DataRow> references to the rows of the table in the synchronized **DataSet**.</span></span>  
  
 <span data-ttu-id="ff48a-106">예를 들어, 다음 코드 샘플에서는 "최하위" XPath 쿼리를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ff48a-106">For example, the following code sample performs a "grandchild" XPath query.</span></span> <span data-ttu-id="ff48a-107">합니다 **데이터 집합** 3 개의 테이블을 사용 하 여 채워집니다. **고객이**, **주문을**, 및 **OrderDetails**합니다.</span><span class="sxs-lookup"><span data-stu-id="ff48a-107">The **DataSet** is filled with three tables: **Customers**, **Orders**, and **OrderDetails**.</span></span> <span data-ttu-id="ff48a-108">이 샘플에서는 부모-자식 관계를 먼저 사이 만들어집니다 합니다 **고객** 및 **주문** 테이블와는 **주문** 및 **OrderDetails** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="ff48a-108">In the sample, a parent-child relation is first created between the **Customers** and **Orders** tables, and between the **Orders** and **OrderDetails** tables.</span></span> <span data-ttu-id="ff48a-109">반환할 XPath 쿼리가 수행 됩니다는 **XmlNodeList** 의 **고객** 노드 위치를 손자 **OrderDetails** 노드에 **ProductID**값이 43 인 노드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff48a-109">An XPath query is then performed to return an **XmlNodeList** of **Customers** nodes where a grandchild **OrderDetails** node has a **ProductID** node with the value of 43.</span></span> <span data-ttu-id="ff48a-110">기본적으로 샘플 쿼리를 사용 하는 XPath가 있는 제품 주문한 고객을 확인 하는 **ProductID** 43입니다.</span><span class="sxs-lookup"><span data-stu-id="ff48a-110">In essence, the sample is using the XPath query to determine which customers have ordered the product that has the **ProductID** of 43.</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection.  
connection.Open()  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
Dim detailAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM [Order Details]", connection)  
detailAdapter.Fill(dataSet, "OrderDetails")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
dataSet.Relations.Add("OrderDetail", _  
  dataSet.Tables("Orders").Columns("OrderID"), _  
dataSet.Tables("OrderDetails").Columns("OrderID"), false).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)   
  
Dim nodeList As XmlNodeList = xmlDoc.DocumentElement.SelectNodes( _  
  "descendant::Customers[*/OrderDetails/ProductID=43]")  
  
Dim dataRow As DataRow  
Dim xmlNode As XmlNode  
  
For Each xmlNode In nodeList  
  dataRow = xmlDoc.GetRowFromElement(CType(xmlNode, XmlElement))  
  
  If Not dataRow Is Nothing then Console.WriteLine(xmlRow(0).ToString())  
Next  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection.  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(dataSet, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(dataSet, "Orders");  
  
SqlDataAdapter detailAdapter = new SqlDataAdapter(  
  "SELECT * FROM [Order Details]", connection);  
detailAdapter.Fill(dataSet, "OrderDetails");  
  
connection.Close();  
  
dataSet.Relations.Add("CustOrders",  
  dataSet.Tables["Customers"].Columns["CustomerID"],  
 dataSet.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
dataSet.Relations.Add("OrderDetail",  
  dataSet.Tables["Orders"].Columns["OrderID"],  
  dataSet.Tables["OrderDetails"].Columns["OrderID"],   
  false).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);   
  
XmlNodeList nodeList = xmlDoc.DocumentElement.SelectNodes(  
  "descendant::Customers[*/OrderDetails/ProductID=43]");  
  
DataRow dataRow;  
foreach (XmlNode xmlNode in nodeList)  
{  
  dataRow = xmlDoc.GetRowFromElement((XmlElement)xmlNode);  
  if (dataRow != null)  
    Console.WriteLine(dataRow[0]);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff48a-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="ff48a-111">See also</span></span>

- [<span data-ttu-id="ff48a-112">데이터 세트 및 XmlDataDocument 동기화</span><span class="sxs-lookup"><span data-stu-id="ff48a-112">DataSet and XmlDataDocument Synchronization</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)
- [<span data-ttu-id="ff48a-113">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="ff48a-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
