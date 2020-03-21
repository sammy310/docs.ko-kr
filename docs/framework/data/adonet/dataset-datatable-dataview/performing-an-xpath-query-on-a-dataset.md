---
title: 데이터 세트에서 XPath 쿼리 수행
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: 5e9a00ab78a57c3c1686d7c87ed8b45d9b2649af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150833"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a><span data-ttu-id="58689-102">데이터 세트에서 XPath 쿼리 수행</span><span class="sxs-lookup"><span data-stu-id="58689-102">Performing an XPath Query on a DataSet</span></span>
<span data-ttu-id="58689-103">동기화된 <xref:System.Data.DataSet> XML Path <xref:System.Xml.XmlDataDocument> 언어(XPath) 쿼리와 같은 XML 서비스를 사용할 수 있으며 **XmlDataDocument에** 액세스하고 **DataSet에** 직접 액세스하는 것보다 특정 기능을 보다 편리하게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58689-103">The relationship between a synchronized <xref:System.Data.DataSet> and <xref:System.Xml.XmlDataDocument> allows you to make use of XML services, such as the XML Path Language (XPath) query, that access the **XmlDataDocument** and can perform certain functionality more conveniently than accessing the **DataSet** directly.</span></span> <span data-ttu-id="58689-104">예를 들어, <xref:System.Data.DataTable> 의 **Select** 메서드를 사용하여 **DataSet의**다른 테이블로 관계를 탐색하는 대신 **DataSet과**동기화된 <xref:System.Xml.XmlNodeList> **XmlDataDocument에서** XPath 쿼리를 수행하여 의 형태로 XML 요소 목록을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58689-104">For example, rather than using the **Select** method of a <xref:System.Data.DataTable> to navigate relationships to other tables in a **DataSet**, you can perform an XPath query on an **XmlDataDocument** that is synchronized with the **DataSet**, to get a list of XML elements in the form of an <xref:System.Xml.XmlNodeList>.</span></span> <span data-ttu-id="58689-105">노드로 <xref:System.Xml.XmlElement> 캐스팅된 **XmlNodeList의**노드는 **XmlDataDocument의** **GetRowFromElement** 메서드에 전달되어 동기화된 **DataSet의**테이블 행에 대한 일치 <xref:System.Data.DataRow> 참조를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58689-105">The nodes in the **XmlNodeList**, cast as <xref:System.Xml.XmlElement> nodes, can then be passed to the **GetRowFromElement** method of the **XmlDataDocument**, to return matching <xref:System.Data.DataRow> references to the rows of the table in the synchronized **DataSet**.</span></span>  
  
 <span data-ttu-id="58689-106">예를 들어, 다음 코드 샘플에서는 "최하위" XPath 쿼리를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="58689-106">For example, the following code sample performs a "grandchild" XPath query.</span></span> <span data-ttu-id="58689-107">**DataSet에는** **고객,** **주문**및 **주문 세부 정보**의 세 가지 테이블이 채워져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58689-107">The **DataSet** is filled with three tables: **Customers**, **Orders**, and **OrderDetails**.</span></span> <span data-ttu-id="58689-108">샘플에서 부모-자식 관계는 **먼저 고객** 및 **주문** 테이블 과 **주문** 및 **OrderDetails** 테이블 간에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="58689-108">In the sample, a parent-child relation is first created between the **Customers** and **Orders** tables, and between the **Orders** and **OrderDetails** tables.</span></span> <span data-ttu-id="58689-109">그런 다음 XPath 쿼리를 수행하여 손자 **OrderDetails** 노드에 값이 43인 **ProductID** 노드가 있는 **고객** 노드의 **XmlNodeList노드를** 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="58689-109">An XPath query is then performed to return an **XmlNodeList** of **Customers** nodes where a grandchild **OrderDetails** node has a **ProductID** node with the value of 43.</span></span> <span data-ttu-id="58689-110">기본적으로 샘플은 XPath 쿼리를 사용하여 **제품 ID가** 43인 제품을 주문한 고객을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="58689-110">In essence, the sample is using the XPath query to determine which customers have ordered the product that has the **ProductID** of 43.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="58689-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58689-111">See also</span></span>

- [<span data-ttu-id="58689-112">데이터 세트 및 XmlDataDocument 동기화</span><span class="sxs-lookup"><span data-stu-id="58689-112">DataSet and XmlDataDocument Synchronization</span></span>](dataset-and-xmldatadocument-synchronization.md)
- [<span data-ttu-id="58689-113">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="58689-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
