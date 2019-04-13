---
title: 데이터 집합에서 XPath 쿼리 수행
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: 29d1e5ae494b2fff4e13886159bb937041152382
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209478"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a>데이터 집합에서 XPath 쿼리 수행
동기화 관계 <xref:System.Data.DataSet> 및 <xref:System.Xml.XmlDataDocument> XML을 활용할 수 있습니다와 같은 서비스 XML Path Language (XPath) 쿼리를 액세스 하는 합니다 **XmlDataDocument** 특정 기능을 수행할 수 있습니다 액세스할 때 보다 더 편리 하 게 합니다 **데이터 집합** 직접. 예를 들어, 사용 하는 대신를 **선택** 메서드를 <xref:System.Data.DataTable> 다른 테이블에 관계를 탐색 하는 **데이터 집합**에서 XPath 쿼리를 수행할 수 있습니다는 **XmlDataDocument**  와 동기화 된 합니다 **데이터 집합**, 형태로 XML 요소의 목록을 가져오려면는 <xref:System.Xml.XmlNodeList>합니다. 노드를 **XmlNodeList**로 캐스팅 <xref:System.Xml.XmlElement> 노드를 전달할 수 있습니다 합니다 **GetRowFromElement** 메서드의 **XmlDataDocument**일치 하는 반환 하려는 경우 <xref:System.Data.DataRow> 동기화 된 테이블의 행에 대 한 참조가 **데이터 집합**합니다.  
  
 예를 들어, 다음 코드 샘플에서는 "최하위" XPath 쿼리를 수행합니다. 합니다 **데이터 집합** 3 개의 테이블을 사용 하 여 채워집니다. **고객이**, **주문을**, 및 **OrderDetails**합니다. 이 샘플에서는 부모-자식 관계를 먼저 사이 만들어집니다 합니다 **고객** 및 **주문** 테이블와는 **주문** 및 **OrderDetails** 테이블입니다. 반환할 XPath 쿼리가 수행 됩니다는 **XmlNodeList** 의 **고객** 노드 위치를 손자 **OrderDetails** 노드에 **ProductID**값이 43 인 노드가 있습니다. 기본적으로 샘플 쿼리를 사용 하는 XPath가 있는 제품 주문한 고객을 확인 하는 **ProductID** 43입니다.  
  
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
  
## <a name="see-also"></a>참고자료

- [데이터 집합 및 XmlDataDocument 동기화](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
