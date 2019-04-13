---
title: DataRelation 중첩
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: 7975e17bd957a822bf3d60d487eb928cee84bd28
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117211"
---
# <a name="nesting-datarelations"></a>DataRelation 중첩
데이터의 관계형 표현에서 각 테이블에는 열이나 열 집합을 사용하여 서로 연결시키는 행이 포함되어 있습니다. ADO.NET <xref:System.Data.DataSet>에서 각 테이블 사이의 관계는 <xref:System.Data.DataRelation>을 사용하여 구현됩니다. 만들 때를 **DataRelation**, 열의 부모-자식 관계는 관계를 통해서만 관리 됩니다. 테이블과 열은 별개의 엔터티입니다. XML에서 제공하는 데이터의 계층적 표현에서 부모-자식 관계는 중첩된 자식 요소를 포함하는 부모 요소에 의해 표현됩니다.  
  
 자식 개체의 중첩을 용이 하 게 때를 **데이터 집합** 와 동기화 되는 <xref:System.Xml.XmlDataDocument> 사용 하 여 XML 데이터를 기록 하거나 **WriteXml**의 **DataRelation** 노출 된 **중첩** 속성입니다. 설정 합니다 **중첩** 의 속성을 **DataRelation** 에 **true** 자식 행을 XML 데이터로 작성 된 부모 열 내에서 중첩 된 관계의 발생 또는 동기화는 **XmlDataDocument**합니다. **중첩** 의 속성을 **DataRelation** 은 **false**, 기본적으로 합니다.  
  
 예를 들어, 다음 사항을 고려 **데이터 집합**합니다.  
  
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
  
 때문에 **중첩** 의 속성을 **DataRelation** 개체 설정 되지 않은 **true** 이 대 한 **데이터 집합**, 자식 개체 중첩 되지 않은 부모 요소에 있는 경우이 **데이터 집합** XML 데이터로 표시 됩니다. XML 표현을 변형 된 **데이터 집합** 포함 된 관련 **데이터 집합**s 중첩 되지 않은 데이터 관계를 사용 하 여 성능이 저하 될 수 있습니다. 데이터 관계를 중첩하는 것이 좋습니다. 이 위해 설정 된 **중첩** 속성을 **true**합니다. 그런 다음 XSLT 스타일시트에서 하향 계층 구조적인 XPath 쿼리 식을 사용하여 데이터를 찾고 변환하는 코드를 작성합니다.  
  
 다음 코드 예제에서는 호출의 결과로 **WriteXml** 에 **데이터 집합**합니다.  
  
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
  
 합니다 **고객** 요소와 **주문** 요소는 형제 요소로 표시 됩니다. 원한다 면를 **주문** 요소가 자신의 해당 부모 요소의 자식으로 표시 되는 데는 **중첩** 속성을 **DataRelation** 로설정해야**true** 다음을 추가 합니다.  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 다음 코드를 보여 줍니다 결과 출력은, 사용 하 여는 **주문** 자신의 해당 부모 요소 내에 중첩 된 요소입니다.  
  
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
  
## <a name="see-also"></a>참고자료

- [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [DataRelation 추가](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)
- [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
