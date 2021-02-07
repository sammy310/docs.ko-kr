---
description: '자세히 알아보기: 쿼리 결과를 통해 페이징'
title: 쿼리 결과를 통해 페이징
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: ead2c74e19cfb81c83c7bf1e73b0c0d7a0a7cc67
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672363"
---
# <a name="paging-through-a-query-result"></a>쿼리 결과를 통해 페이징

쿼리 결과 페이징은 쿼리의 결과를 작은 단위의 데이터 하위 집합, 즉 페이지로 반환하는 프로세스입니다. 이 방법은 관리하기 쉬운 작은 청크 단위로 결과를 표시하기 위해 일반적으로 사용됩니다.  
  
 **DataAdapter** 는 **Fill** 메서드의 오버 로드를 통해 데이터 페이지를 반환 하는 기능을 제공 합니다. 그러나 **DataAdapter** 에서 요청된 레코드로만 대상 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet>를 채우더라도 전체 쿼리를 반환하기 위한 리소스는 계속 사용되기 때문에 대량의 쿼리 결과를 페이징할 경우에는 다른 방법을 사용하는 것이 좋습니다. 전체 쿼리를 반환하기 위한 리소스를 사용하지 않고 데이터 소스에서 데이터 페이지를 반환하려면 필요한 쿼리에만 반환되는 행을 줄이도록 쿼리에 추가 조건을 지정합니다.  
  
 **Fill** 메서드를 사용 하 여 데이터 페이지를 반환 하려면 데이터 페이지의 첫 번째 레코드에 대해 **startRecord** 매개 변수를 지정 하 고 데이터 페이지의 레코드 수에 대해 **maxRecords** 매개 변수를 지정 합니다.  
  
 다음 코드 예제에서는 **Fill** 메서드를 사용 하 여 페이지 크기가 5 인 쿼리 결과의 첫 번째 페이지를 반환 하는 방법을 보여 줍니다.  
  
```vb  
Dim currentIndex As Integer = 0  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT * FROM dbo.Orders ORDER BY OrderID"  
' Assumes that connection is a valid SqlConnection object.  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
int currentIndex = 0;  
int pageSize = 5;  
  
string orderSQL = "SELECT * FROM Orders ORDER BY OrderID";  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 이전 예제에서 **DataSet** 는 다섯 개의 레코드로만 채워지지만 **Orders** 테이블 전체가 반환됩니다. **데이터 집합** 을 동일한 5 개의 레코드로 채우지만 5 개의 레코드만 반환 하려면 다음 코드 예제와 같이 SQL 문에 TOP 및 WHERE 절을 사용 합니다.  
  
```vb  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT TOP " & pageSize & _  
  " * FROM Orders ORDER BY OrderID"  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Orders")
```  
  
```csharp  
int pageSize = 5;  
  
string orderSQL = "SELECT TOP " + pageSize +
  " * FROM Orders ORDER BY OrderID";  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Orders");  
```  
  
 이 방법으로 쿼리 결과를 페이징할 때는 다음 코드 예제와 같이 행의 순서를 나타내는 고유 ID를 유지하여 다음 레코드 페이지를 반환하기 위해 해당 고유 ID를 명령에 전달해야 합니다.  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 **StartRecord** 및 **maxRecords** 매개 변수를 사용 하는 **Fill** 메서드의 오버 로드를 사용 하 여 다음 레코드 페이지를 반환 하려면 현재 레코드 인덱스를 페이지 크기로 증가 시키고 표를 채웁니다. 데이터베이스 서버에서는 **DataSet** 에 레코드 페이지가 하나만 추가되더라도 전체 쿼리 결과를 반환합니다. 다음 코드 예제에서는 다음 데이터 페이지로 채워지기 전에 테이블 행이 지워집니다. 데이터베이스 서버로의 트립을 줄이기 위해 반환되는 행의 일부를 로컬 캐시에 보존할 수도 있습니다.  
  
```vb  
currentIndex = currentIndex + pageSize  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
currentIndex += pageSize;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 데이터베이스 서버에서 전체 쿼리를 반환하지 않고 다음 레코드 페이지를 반환하도록 하려면 SELECT 문에 제한 조건을 지정합니다. 이전 예제에서는 마지막 반환 레코드를 유지하므로 해당 레코드를 WHERE 절에 사용하여 다음 코드 예제와 같이 쿼리에 시작 지점을 지정할 수 있습니다.  
  
```vb  
orderSQL = "SELECT TOP " & pageSize & _  
  " * FROM Orders WHERE OrderID > " & lastRecord & " ORDER BY OrderID"  
adapter.SelectCommand.CommandText = orderSQL  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, "Orders")  
```  
  
```csharp  
orderSQL = "SELECT TOP " + pageSize +
  " * FROM Orders WHERE OrderID > " + lastRecord + " ORDER BY OrderID";  
adapter.SelectCommand.CommandText = orderSQL;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, "Orders");  
```  
  
## <a name="see-also"></a>참고 항목

- [DataAdapters 및 DataReaders](dataadapters-and-datareaders.md)
- [ADO.NET 개요](ado-net-overview.md)
