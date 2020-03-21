---
title: 쿼리 결과를 통해 페이징
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 2e7fb97e5c0cb42deff43c411f47e8d30e2257ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149390"
---
# <a name="paging-through-a-query-result"></a><span data-ttu-id="ab6c5-102">쿼리 결과를 통해 페이징</span><span class="sxs-lookup"><span data-stu-id="ab6c5-102">Paging Through a Query Result</span></span>
<span data-ttu-id="ab6c5-103">쿼리 결과 페이징은 쿼리의 결과를 작은 단위의 데이터 하위 집합, 즉 페이지로 반환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-103">Paging through a query result is the process of returning the results of a query in smaller subsets of data, or pages.</span></span> <span data-ttu-id="ab6c5-104">이 방법은 관리하기 쉬운 작은 청크 단위로 결과를 표시하기 위해 일반적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-104">This is a common practice for displaying results to a user in small, easy-to-manage chunks.</span></span>  
  
 <span data-ttu-id="ab6c5-105">**DataAdapter는** **채우기** 메서드의 오버로드를 통해 데이터 페이지만 반환하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-105">The **DataAdapter** provides a facility for returning only a page of data, through overloads of the **Fill** method.</span></span> <span data-ttu-id="ab6c5-106">그러나 **DataAdapter가** 대상을 <xref:System.Data.DataTable> 채우거나 요청된 레코드만 사용하지만 <xref:System.Data.DataSet> 전체 쿼리를 반환하는 리소스가 여전히 사용되기 때문에 큰 쿼리 결과를 페이징하는 데 는 최선의 선택이 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-106">However, this might not be the best choice for paging through large query results because, although the **DataAdapter** fills the target <xref:System.Data.DataTable> or <xref:System.Data.DataSet> with only the requested records, the resources to return the entire query are still used.</span></span> <span data-ttu-id="ab6c5-107">전체 쿼리를 반환하기 위한 리소스를 사용하지 않고 데이터 소스에서 데이터 페이지를 반환하려면 필요한 쿼리에만 반환되는 행을 줄이도록 쿼리에 추가 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-107">To return a page of data from a data source without using the resources to return the entire query, specify additional criteria for your query that reduce the rows returned to only those required.</span></span>  
  
 <span data-ttu-id="ab6c5-108">**채우기** 메서드를 사용하여 데이터 페이지를 반환하려면 데이터 페이지의 첫 번째 레코드에 대해 **startRecord** 매개 변수를 지정하고 데이터 페이지의 레코드 수에 대해 **maxRecords** 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-108">To use the **Fill** method to return a page of data, specify a **startRecord** parameter, for the first record in the page of data, and a **maxRecords** parameter, for the number of records in the page of data.</span></span>  
  
 <span data-ttu-id="ab6c5-109">다음 코드 예제에서는 **채우기** 메서드를 사용하여 페이지 크기가 5개의 레코드인 쿼리 결과의 첫 번째 페이지를 반환하는 방법을 보여 주십니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-109">The following code example shows how to use the **Fill** method to return the first page of a query result where the page size is five records.</span></span>  
  
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
  
 <span data-ttu-id="ab6c5-110">이전 예제에서 **DataSet은** 5개의 레코드로만 채워지지만 전체 **Orders** 테이블이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-110">In the previous example, the **DataSet** is only filled with five records, but the entire **Orders** table is returned.</span></span> <span data-ttu-id="ab6c5-111">**DataSet을** 동일한 5개의 레코드로 채우되 5개의 레코드만 반환하려면 다음 코드 예제와 같이 SQL 문의 TOP 및 WHERE 절을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-111">To fill the **DataSet** with those same five records, but only return five records, use the TOP and WHERE clauses in your SQL statement, as in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="ab6c5-112">이 방법으로 쿼리 결과를 페이징할 때는 다음 코드 예제와 같이 행의 순서를 나타내는 고유 ID를 유지하여 다음 레코드 페이지를 반환하기 위해 해당 고유 ID를 명령에 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-112">Note that, when paging through the query results in this way, you must preserve the unique identifier that orders the rows, in order to pass the unique ID to the command to return the next page of records, as shown in the following code example.</span></span>  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 <span data-ttu-id="ab6c5-113">**startRecord** 및 **maxRecords** 매개 변수를 사용하는 **채우기** 메서드의 오버로드를 사용하여 레코드의 다음 페이지를 반환하려면 현재 레코드 인덱스를 페이지 크기로 증분하고 테이블을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-113">To return the next page of records using the overload of the **Fill** method that takes the **startRecord** and **maxRecords** parameters, increment the current record index by the page size and fill the table.</span></span> <span data-ttu-id="ab6c5-114">데이터베이스 서버는 레코드의 한 페이지만 **DataSet에**추가되더라도 전체 쿼리 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-114">Remember that the database server returns the entire query results even though only one page of records is added to the **DataSet**.</span></span> <span data-ttu-id="ab6c5-115">다음 코드 예제에서는 다음 데이터 페이지로 채워지기 전에 테이블 행이 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-115">In the following code example, the table rows are cleared before they are filled with the next page of data.</span></span> <span data-ttu-id="ab6c5-116">데이터베이스 서버로의 트립을 줄이기 위해 반환되는 행의 일부를 로컬 캐시에 보존할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-116">You might want to preserve a certain number of returned rows in a local cache to reduce trips to the database server.</span></span>  
  
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
  
 <span data-ttu-id="ab6c5-117">데이터베이스 서버에서 전체 쿼리를 반환하지 않고 다음 레코드 페이지를 반환하도록 하려면 SELECT 문에 제한 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-117">To return the next page of records without having the database server return the entire query, specify restrictive criteria to the SELECT statement.</span></span> <span data-ttu-id="ab6c5-118">이전 예제에서는 마지막 반환 레코드를 유지하므로 해당 레코드를 WHERE 절에 사용하여 다음 코드 예제와 같이 쿼리에 시작 지점을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-118">Because the preceding example preserved the last record returned, you can use it in the WHERE clause to specify a starting point for the query, as shown in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ab6c5-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab6c5-119">See also</span></span>

- [<span data-ttu-id="ab6c5-120">DataAdapter 및 DataReader</span><span class="sxs-lookup"><span data-stu-id="ab6c5-120">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="ab6c5-121">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="ab6c5-121">ADO.NET Overview</span></span>](ado-net-overview.md)
