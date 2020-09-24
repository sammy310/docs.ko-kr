---
title: DataAdapter에서 DataSet 채우기
description: 데이터 원본에 독립적인 일관 된 관계형 프로그래밍 모델을 제공 하는 ADO.NET의 DataAdapter에서 데이터 집합을 채우는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3fa0ac7d-e266-4954-bfac-3fbe2f913153
ms.openlocfilehash: ac84af884238b166266d4206802878c1e21169fd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177412"
---
# <a name="populating-a-dataset-from-a-dataadapter"></a><span data-ttu-id="6d4ac-103">DataAdapter에서 DataSet 채우기</span><span class="sxs-lookup"><span data-stu-id="6d4ac-103">Populating a DataSet from a DataAdapter</span></span>

<span data-ttu-id="6d4ac-104">ADO.NET는 <xref:System.Data.DataSet> 데이터 원본에 독립적인 일관 된 관계형 프로그래밍 모델을 제공 하는 데이터의 메모리 상주 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-104">The ADO.NET <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model independent of the data source.</span></span> <span data-ttu-id="6d4ac-105">`DataSet` 은 테이블 및 제약 조건과 테이블 간의 관계를 포함하는 완전한 데이터 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-105">The `DataSet` represents a complete set of data that includes tables, constraints, and relationships among the tables.</span></span> <span data-ttu-id="6d4ac-106">`DataSet` 은 데이터 소스에 독립적입니다. 따라서 `DataSet` 은 애플리케이션에 대해 로컬인 데이터뿐 아니라 여러 데이터 소스의 데이터도 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-106">Because the `DataSet` is independent of the data source, a `DataSet` can include data local to the application, and data from multiple data sources.</span></span> <span data-ttu-id="6d4ac-107">기존 데이터 소스와의 상호 작용은 `DataAdapter`를 통해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-107">Interaction with existing data sources is controlled through the `DataAdapter`.</span></span>  
  
 <span data-ttu-id="6d4ac-108">`SelectCommand` 의 `DataAdapter` 속성은 데이터 소스에서 데이터를 검색하는 `Command` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-108">The `SelectCommand` property of the `DataAdapter` is a `Command` object that retrieves data from the data source.</span></span> <span data-ttu-id="6d4ac-109">`InsertCommand`의 `UpdateCommand`, `DeleteCommand` 및 `DataAdapter` 속성은 `Command` 의 데이터에 대한 수정 내용에 따라 데이터 소스의 데이터에 대한 업데이트를 관리하는 `DataSet`개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-109">The `InsertCommand`, `UpdateCommand`, and `DeleteCommand` properties of the `DataAdapter` are `Command` objects that manage updates to the data in the data source according to modifications made to the data in the `DataSet`.</span></span> <span data-ttu-id="6d4ac-110">이러한 속성은 [dataadapter를 사용 하 여 데이터 원본 업데이트](updating-data-sources-with-dataadapters.md)에 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-110">These properties are covered in more detail in [Updating Data Sources with DataAdapters](updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="6d4ac-111">`Fill` 의 `DataAdapter` 메서드는 `DataSet` 의 `SelectCommand` 결과로 `DataAdapter`을 채우는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-111">The `Fill` method of the `DataAdapter` is used to populate a `DataSet` with the results of the `SelectCommand` of the `DataAdapter`.</span></span> <span data-ttu-id="6d4ac-112">`Fill` 은 채울 `DataSet` 과 `DataTable` 개체 또는 `DataTable` 에서 반환된 행으로 채울 `SelectCommand`의 이름을 인수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-112">`Fill` takes as its arguments a `DataSet` to be populated, and a `DataTable` object, or the name of the `DataTable` to be filled with the rows returned from the `SelectCommand`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6d4ac-113">`DataAdapter` 를 사용하여 모든 테이블을 검색하는 경우 시간이 많이 걸리며, 특히 테이블에 많은 행이 있는 경우 더욱 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-113">Using the `DataAdapter` to retrieve all of a table takes time, especially if there are many rows in the table.</span></span> <span data-ttu-id="6d4ac-114">이는 데이터베이스에 액세스하여 데이터를 찾아서 처리한 다음 클라이언트로 데이터를 전송하는 데 많은 시간이 걸리기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-114">This is because accessing the database, locating and processing the data, and then transferring the data to the client is time-consuming.</span></span> <span data-ttu-id="6d4ac-115">모든 테이블을 클라이언트로 가져오는 경우 서버의 모든 행이 잠기는 문제도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-115">Pulling all of the table to the client also locks all of the rows on the server.</span></span> <span data-ttu-id="6d4ac-116">이 경우 `WHERE` 절을 사용하여 클라이언트에 반환되는 행 수를 대폭 줄이면 성능을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-116">To improve performance, you can use the `WHERE` clause to greatly reduce the number of rows returned to the client.</span></span> <span data-ttu-id="6d4ac-117">`SELECT` 문에 필요한 열을 명시적으로 나열하여 클라이언트에 반환되는 데이터의 양을 줄일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-117">You can also reduce the amount of data returned to the client by only explicitly listing required columns in the `SELECT` statement.</span></span> <span data-ttu-id="6d4ac-118">한 번에 몇 백 개씩 행을 일괄적으로 검색함으로써 클라이언트에서 현재 일괄 검색 작업이 완료되면 다음 일괄 검색 작업을 시작하는 것도 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-118">Another good workaround is to retrieve the rows in batches (such as several hundred rows at a time) and only retrieve the next batch when the client is finished with the current batch.</span></span>  
  
 <span data-ttu-id="6d4ac-119">`Fill` 메서드는 `DataReader` 개체를 암시적으로 사용하여 `DataSet`의 테이블 행을 채울 데이터와 `DataSet`에 테이블을 만드는 데 사용되는 열 이름 및 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-119">The `Fill` method uses the `DataReader` object implicitly to return the column names and types that are used to create the tables in the `DataSet`, and the data to populate the rows of the tables in the `DataSet`.</span></span> <span data-ttu-id="6d4ac-120">테이블과 열은 없는 경우에만 만들어지고 있는 경우 `Fill` 에서 기존의 `DataSet` 스키마를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-120">Tables and columns are only created if they do not already exist; otherwise `Fill` uses the existing `DataSet` schema.</span></span> <span data-ttu-id="6d4ac-121">열 유형은 [ADO.NET의 데이터 형식 매핑](data-type-mappings-in-ado-net.md)테이블에 따라 .NET Framework 형식으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-121">Column types are created as .NET Framework types according to the tables in [Data Type Mappings in ADO.NET](data-type-mappings-in-ado-net.md).</span></span> <span data-ttu-id="6d4ac-122">기본 키는 데이터 원본 및에 존재 하지 않는 한 생성 되지 않습니다 `DataAdapter` **.**`MissingSchemaAction`</span><span class="sxs-lookup"><span data-stu-id="6d4ac-122">Primary keys are not created unless they exist in the data source and `DataAdapter`**.**`MissingSchemaAction`</span></span> <span data-ttu-id="6d4ac-123">는 `MissingSchemaAction` **.** 로 설정 됩니다. `AddWithKey`</span><span class="sxs-lookup"><span data-stu-id="6d4ac-123">is set to `MissingSchemaAction`**.**`AddWithKey`.</span></span> <span data-ttu-id="6d4ac-124">`Fill` 에서 테이블의 기본 키가 있음을 발견하면 기본 키 열 값이 데이터 소스에서 반환된 행의 값과 일치하는 행의 데이터 소스 데이터로 `DataSet` 의 데이터를 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-124">If `Fill` finds that a primary key exists for a table, it will overwrite data in the `DataSet` with data from the data source for rows where the primary key column values match those of the row returned from the data source.</span></span> <span data-ttu-id="6d4ac-125">기본 키가 없으면 해당 데이터가 `DataSet`의 테이블에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-125">If no primary key is found, the data is appended to the tables in the `DataSet`.</span></span> <span data-ttu-id="6d4ac-126">`Fill` 는를 채울 때 있을 수 있는 모든 매핑을 사용 `DataSet` 합니다 ( [DataAdapter DataTable 및 DataColumn 매핑](dataadapter-datatable-and-datacolumn-mappings.md)참조).</span><span class="sxs-lookup"><span data-stu-id="6d4ac-126">`Fill` uses any mappings that may exist when you populate the `DataSet` (see [DataAdapter DataTable and DataColumn Mappings](dataadapter-datatable-and-datacolumn-mappings.md)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6d4ac-127">`SelectCommand` 가 OUTER JOIN의 결과를 반환하면 `DataAdapter` 는 결과 `PrimaryKey` 에 대해 `DataTable`값을 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-127">If the `SelectCommand` returns the results of an OUTER JOIN, the `DataAdapter` does not set a `PrimaryKey` value for the resulting `DataTable`.</span></span> <span data-ttu-id="6d4ac-128">행 중복 문제를 해결하려면 `PrimaryKey` 를 직접 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-128">You must define the `PrimaryKey` yourself to make sure that duplicate rows are resolved correctly.</span></span> <span data-ttu-id="6d4ac-129">자세한 내용은 [기본 키 정의](./dataset-datatable-dataview/defining-primary-keys.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-129">For more information, see [Defining Primary Keys](./dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
 <span data-ttu-id="6d4ac-130">다음 코드 예제에서는 Microsoft SQL Server <xref:System.Data.SqlClient.SqlDataAdapter> 데이터베이스에 대한 <xref:System.Data.SqlClient.SqlConnection> 을 사용하는 `Northwind` 의 인스턴스를 만들고 <xref:System.Data.DataTable> 의 `DataSet` 을 고객 목록으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-130">The following code example creates an instance of a <xref:System.Data.SqlClient.SqlDataAdapter> that uses a <xref:System.Data.SqlClient.SqlConnection> to the Microsoft SQL Server `Northwind` database and populates a <xref:System.Data.DataTable> in a `DataSet` with the list of customers.</span></span> <span data-ttu-id="6d4ac-131"><xref:System.Data.SqlClient.SqlConnection> 생성자에 전달되는 <xref:System.Data.SqlClient.SqlDataAdapter> 인수와 SQL 문은 <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A> 의 <xref:System.Data.SqlClient.SqlDataAdapter>속성을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-131">The SQL statement and <xref:System.Data.SqlClient.SqlConnection> arguments passed to the <xref:System.Data.SqlClient.SqlDataAdapter> constructor are used to create the <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A> property of the <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d4ac-132">예제</span><span class="sxs-lookup"><span data-stu-id="6d4ac-132">Example</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim queryString As String = _  
  "SELECT CustomerID, CompanyName FROM dbo.Customers"  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  queryString, connection)  
  
Dim customers As DataSet = New DataSet  
adapter.Fill(customers, "Customers")  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
string queryString =
  "SELECT CustomerID, CompanyName FROM dbo.Customers";  
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
```  
  
> [!NOTE]
> <span data-ttu-id="6d4ac-133">이 예제의 코드에서는 `Connection`을 명시적으로 열거나 닫지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-133">The code shown in this example does not explicitly open and close the `Connection`.</span></span> <span data-ttu-id="6d4ac-134">`Fill` 메서드는 연결이 아직 열려 있지 않으면 `Connection` 에서 사용하고 있는 `DataAdapter` 을 암시적으로 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-134">The `Fill` method implicitly opens the `Connection` that the `DataAdapter` is using if it finds that the connection is not already open.</span></span> <span data-ttu-id="6d4ac-135">`Fill` 에서 연결을 연 경우 `Fill` 이 완료되면 연결도 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-135">If `Fill` opened the connection, it also closes the connection when `Fill` is finished.</span></span> <span data-ttu-id="6d4ac-136">`Fill` 또는 `Update`와 같은 단일 작업을 처리할 경우 이렇게 하면 코드가 간단해집니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-136">This can simplify your code when you deal with a single operation such as a `Fill` or an `Update`.</span></span> <span data-ttu-id="6d4ac-137">그러나 연결이 열려 있어야 하는 여러 작업을 수행 중인 경우에는 `Open` 의 `Connection`메서드를 명시적으로 호출하고 데이터 소스에 대한 작업을 수행한 다음 `Close` 의 `Connection`메서드를 호출하여 애플리케이션의 성능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-137">However, if you are performing multiple operations that require an open connection, you can improve the performance of your application by explicitly calling the `Open` method of the `Connection`, performing the operations against the data source, and then calling the `Close` method of the `Connection`.</span></span> <span data-ttu-id="6d4ac-138">다른 클라이언트 애플리케이션에서 사용할 리소스를 사용 가능한 상태로 만들려면 데이터 소스에 연결되어 있는 시간을 가능한 한 짧게 유지하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-138">You should try to keep connections to the data source open as briefly as possible to free resources for use by other client applications.</span></span>  
  
## <a name="multiple-result-sets"></a><span data-ttu-id="6d4ac-139">여러 결과 집합</span><span class="sxs-lookup"><span data-stu-id="6d4ac-139">Multiple Result Sets</span></span>  

 <span data-ttu-id="6d4ac-140">`DataAdapter` 는 여러 결과 집합을 발견하면 `DataSet`에 여러 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-140">If the `DataAdapter` encounters multiple result sets, it creates multiple tables in the `DataSet`.</span></span> <span data-ttu-id="6d4ac-141">테이블에는 Table0부터 시작하는 증분 기본 이름인 Table*N*이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-141">The tables are given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span> <span data-ttu-id="6d4ac-142">테이블 이름이 인수로 `Fill` 메서드에 전달되면 테이블에는 TableName0부터 시작하는 증분 기본 이름인 TableName*N*이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-142">If a table name is passed as an argument to the `Fill` method, the tables are given an incremental default name of TableName*N*, starting with "TableName" for TableName0.</span></span>  
  
## <a name="populating-a-dataset-from-multiple-dataadapters"></a><span data-ttu-id="6d4ac-143">여러 DataAdapter에서 DataSet 채우기</span><span class="sxs-lookup"><span data-stu-id="6d4ac-143">Populating a DataSet from Multiple DataAdapters</span></span>  

 <span data-ttu-id="6d4ac-144">에서 원하는 수의 `DataAdapter` 개체를 사용할 수 있습니다 `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="6d4ac-144">Any number of `DataAdapter` objects can be used with a `DataSet`.</span></span> <span data-ttu-id="6d4ac-145">`DataAdapter` 는 각각 하나 이상의 `DataTable` 개체를 채우고 업데이트를 다시 관련 데이터 소스에 적용하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-145">Each `DataAdapter` can be used to fill one or more `DataTable` objects and resolve updates back to the relevant data source.</span></span> <span data-ttu-id="6d4ac-146">`DataRelation` 및 `Constraint` 개체를 `DataSet` 에 로컬로 추가하면 각기 다른 데이터 소스의 데이터를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-146">`DataRelation` and `Constraint` objects can be added to the `DataSet` locally, which enables you to relate data from dissimilar data sources.</span></span> <span data-ttu-id="6d4ac-147">예를 들어, `DataSet` 은 Microsoft SQL Server 데이터베이스, OLE DB를 통해 노출된 IBM DB2 데이터베이스, XML을 스트리밍하는 데이터 소스의 데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-147">For example, a `DataSet` can contain data from a Microsoft SQL Server database, an IBM DB2 database exposed through OLE DB, and a data source that streams XML.</span></span> <span data-ttu-id="6d4ac-148">하나 이상의 `DataAdapter` 개체에서 각 데이터 소스와의 통신을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-148">One or more `DataAdapter` objects can handle communication to each data source.</span></span>  
  
### <a name="example"></a><span data-ttu-id="6d4ac-149">예제</span><span class="sxs-lookup"><span data-stu-id="6d4ac-149">Example</span></span>  

 <span data-ttu-id="6d4ac-150">다음 코드 예제에서는 Microsoft SQL Server에 있는 `Northwind` 데이터베이스의 고객 목록과 Microsoft Access 2000에 저장된 `Northwind` 데이터베이스의 주문 목록을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-150">The following code example populates a list of customers from the `Northwind` database on Microsoft SQL Server, and a list of orders from the `Northwind` database stored in Microsoft Access 2000.</span></span> <span data-ttu-id="6d4ac-151">채워진 테이블은 `DataRelation`에 연결되고 고객 목록이 해당 고객의 주문과 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-151">The filled tables are related with a `DataRelation`, and the list of customers is then displayed with the orders for that customer.</span></span> <span data-ttu-id="6d4ac-152">개체에 대 한 자세한 내용은 `DataRelation` [Datarelations 추가](./dataset-datatable-dataview/adding-datarelations.md) 및 [datarelations 탐색](./dataset-datatable-dataview/navigating-datarelations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-152">For more information about `DataRelation` objects, see [Adding DataRelations](./dataset-datatable-dataview/adding-datarelations.md) and [Navigating DataRelations](./dataset-datatable-dataview/navigating-datarelations.md).</span></span>  
  
```vb  
' Assumes that customerConnection is a valid SqlConnection object.  
' Assumes that orderConnection is a valid OleDbConnection object.  
Dim custAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers", customerConnection)  
  
Dim ordAdapter As OleDbDataAdapter = New OleDbDataAdapter( _  
  "SELECT * FROM Orders", orderConnection)  
  
Dim customerOrders As DataSet = New DataSet()  
custAdapter.Fill(customerOrders, "Customers")  
ordAdapter.Fill(customerOrders, "Orders")  
  
Dim relation As DataRelation = _  
  customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustomerID"), _
  customerOrders.Tables("Orders").Columns("CustomerID"))  
  
Dim pRow, cRow As DataRow  
For Each pRow In customerOrders.Tables("Customers").Rows  
  Console.WriteLine(pRow("CustomerID").ToString())  
  
  For Each cRow In pRow.GetChildRows(relation)  
    Console.WriteLine(vbTab & cRow("OrderID").ToString())  
  Next  
Next  
```  
  
```csharp  
// Assumes that customerConnection is a valid SqlConnection object.  
// Assumes that orderConnection is a valid OleDbConnection object.  
SqlDataAdapter custAdapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers", customerConnection);  
OleDbDataAdapter ordAdapter = new OleDbDataAdapter(  
  "SELECT * FROM Orders", orderConnection);  
  
DataSet customerOrders = new DataSet();  
  
custAdapter.Fill(customerOrders, "Customers");  
ordAdapter.Fill(customerOrders, "Orders");  
  
DataRelation relation = customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustomerID"],  
  customerOrders.Tables["Orders"].Columns["CustomerID"]);  
  
foreach (DataRow pRow in customerOrders.Tables["Customers"].Rows)  
{  
  Console.WriteLine(pRow["CustomerID"]);  
   foreach (DataRow cRow in pRow.GetChildRows(relation))  
    Console.WriteLine("\t" + cRow["OrderID"]);  
}  
```  
  
## <a name="sql-server-decimal-type"></a><span data-ttu-id="6d4ac-153">SQL Server Decimal 형식</span><span class="sxs-lookup"><span data-stu-id="6d4ac-153">SQL Server Decimal Type</span></span>  

 <span data-ttu-id="6d4ac-154">기본적으로에서는 `DataSet` .NET Framework 데이터 형식을 사용 하 여 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-154">By default, the `DataSet` stores data by using .NET Framework data types.</span></span> <span data-ttu-id="6d4ac-155">대부분의 애플리케이션에서 이 형식을 사용하면 데이터 소스 정보를 간편하게 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-155">For most applications, these provide a convenient representation of data source information.</span></span> <span data-ttu-id="6d4ac-156">그러나 이 표현은 데이터 소스의 데이터 형식이 SQL Server decimal 또는 숫자 데이터 형식인 경우 문제를 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-156">However, this representation may cause a problem when the data type in the data source is a SQL Server decimal or numeric data type.</span></span> <span data-ttu-id="6d4ac-157">.NET Framework `decimal` 데이터 형식은 최대 28 개의 유효 숫자를 허용 하는 반면 SQL Server `decimal` 데이터 형식은 38 개의 유효 숫자를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-157">The .NET Framework `decimal` data type allows a maximum of 28 significant digits, whereas the SQL Server `decimal` data type allows 38 significant digits.</span></span> <span data-ttu-id="6d4ac-158">`SqlDataAdapter` 작업 중에 `Fill` 에서 SQL Server `decimal` 필드의 정밀도가 28자보다 크다고 판단하면 현재 행은 `DataTable`에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-158">If the `SqlDataAdapter` determines during a `Fill` operation that the precision of a SQL Server `decimal` field is larger than 28 characters, the current row is not added to the `DataTable`.</span></span> <span data-ttu-id="6d4ac-159">대신 `FillError` 이벤트가 발생하므로 정밀도가 손실되는지 여부를 확인하여 적절하게 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-159">Instead the `FillError` event occurs, which enables you to determine whether a loss of precision will occur, and respond appropriately.</span></span> <span data-ttu-id="6d4ac-160">이벤트에 대 한 자세한 내용은 `FillError` [DataAdapter 이벤트 처리](handling-dataadapter-events.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-160">For more information about the `FillError` event, see [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span> <span data-ttu-id="6d4ac-161">`decimal` 개체를 사용하고 <xref:System.Data.SqlClient.SqlDataReader> 메서드를 호출하여 SQL Server <xref:System.Data.SqlClient.SqlDataReader.GetSqlDecimal%2A> 값을 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-161">To get the SQL Server `decimal` value, you can also use a <xref:System.Data.SqlClient.SqlDataReader> object and call the <xref:System.Data.SqlClient.SqlDataReader.GetSqlDecimal%2A> method.</span></span>  
  
 <span data-ttu-id="6d4ac-162">ADO.NET 2.0에는의에 대 한 향상 된 지원이 도입 <xref:System.Data.SqlTypes> `DataSet` 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-162">ADO.NET 2.0 introduced enhanced support for <xref:System.Data.SqlTypes> in the `DataSet`.</span></span> <span data-ttu-id="6d4ac-163">자세한 내용은 [SqlTypes and the DataSet](./sql/sqltypes-and-the-dataset.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-163">For more information, see [SqlTypes and the DataSet](./sql/sqltypes-and-the-dataset.md).</span></span>  
  
## <a name="ole-db-chapters"></a><span data-ttu-id="6d4ac-164">OLE DB 장</span><span class="sxs-lookup"><span data-stu-id="6d4ac-164">OLE DB Chapters</span></span>  

 <span data-ttu-id="6d4ac-165">계층적 행 집합 또는 장(OLE DB 형식 `DBTYPE_HCHAPTER`, ADO 형식 `adChapter`)을 사용하여 `DataSet`의 내용을 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-165">Hierarchical rowsets, or chapters (OLE DB type `DBTYPE_HCHAPTER`, ADO type `adChapter`) can be used to fill the contents of a `DataSet`.</span></span> <span data-ttu-id="6d4ac-166"><xref:System.Data.OleDb.OleDbDataAdapter> 에서 `Fill` 작업 중에 장으로 나뉜 열을 발견하면 해당 열에 대해 `DataTable` 이 만들어지고 테이블은 그 장의 열과 행으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-166">When the <xref:System.Data.OleDb.OleDbDataAdapter> encounters a chaptered column during a `Fill` operation, a `DataTable` is created for the chaptered column, and that table is filled with the columns and rows from the chapter.</span></span> <span data-ttu-id="6d4ac-167">장으로 나뉜 열에 대해 만들어진 테이블은 부모 테이블 이름과 장으로 나뉜 열 이름을 모두 사용하여 "*ParentTableNameChapteredColumnName*" 형식으로 이름이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-167">The table created for the chaptered column is named by using both the parent table name and the chaptered column name in the form "*ParentTableNameChapteredColumnName*".</span></span> <span data-ttu-id="6d4ac-168">장으로 나뉜 열 이름과 일치하는 테이블이 이미 `DataSet` 에 있으면 현재 테이블이 장 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-168">If a table already exists in the `DataSet` that matches the name of the chaptered column, the current table is filled with the chapter data.</span></span> <span data-ttu-id="6d4ac-169">장에 있는 열과 일치하는 열이 기존 테이블에 없으면 새 열이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-169">If there is no column in an existing table that matches a column found in the chapter, a new column is added.</span></span>  
  
 <span data-ttu-id="6d4ac-170">`DataSet` 의 테이블이 장으로 나뉜 열의 데이터로 채워지기 전에 계층적 행 집합의 부모 테이블과 자식 테이블 사이에는 정수 열을 부모 테이블과 자식 테이블에 모두 추가하고 부모 열을 자동 증분으로 설정한 다음 두 테이블에서 추가된 열을 사용하여 `DataRelation` 을 만듦으로써 관계가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-170">Before the tables in the `DataSet` are filled with the data in the chaptered columns, a relation is created between the parent and child tables of the hierarchical rowset by adding an integer column to both the parent and child table, setting the parent column to auto-increment, and creating a `DataRelation` using the added columns from both tables.</span></span> <span data-ttu-id="6d4ac-171">추가된 관계의 이름은 부모 테이블과 장의 열 이름을 사용하여 "*ParentTableNameChapterColumnName*" 형식으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-171">The added relation is named by using the parent table and chapter column names in the form "*ParentTableNameChapterColumnName*".</span></span>  
  
 <span data-ttu-id="6d4ac-172">`DataSet`에는 관련 열만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-172">Note that the related column only exists in the `DataSet`.</span></span> <span data-ttu-id="6d4ac-173">다음에 데이터 소스에서 채우기 작업이 수행되면 변경 내용이 기존 행으로 병합되지 않고 새 행이 테이블에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-173">Subsequent fills from the data source can cause new rows to be added to the tables instead of changes being merged into existing rows.</span></span>  
  
 <span data-ttu-id="6d4ac-174">또한 `DataAdapter.Fill` 을 사용하는 `DataTable`오버로드를 사용하면 해당 테이블만 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-174">Note also that, if you use the `DataAdapter.Fill` overload that takes a `DataTable`, only that table will be filled.</span></span> <span data-ttu-id="6d4ac-175">자동 증분 정수 열은 여전히 테이블에 추가되지만 자식 테이블이 만들어지거나 채워지지 않으며 관계도 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-175">An auto-incrementing integer column will still be added to the table, but no child table will be created or filled, and no relation will be created.</span></span>  
  
 <span data-ttu-id="6d4ac-176">다음 예제에서는 MSDataShape 공급자를 사용하여 고객 목록에 있는 각 고객의 주문에 대해 장 열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-176">The following example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span> <span data-ttu-id="6d4ac-177">그런 다음 `DataSet` 이 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-177">A `DataSet` is then filled with the data.</span></span>  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection( _  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" & _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=northwind")  
  
Dim adapter As OleDbDataAdapter = New OleDbDataAdapter( _  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " & _  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS Orders " & _  
  "RELATE CustomerID TO CustomerID)", connection)  
  
Dim customers As DataSet = New DataSet()  
  
adapter.Fill(customers, "Customers")  
End Using  
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection("Provider=MSDataShape;Data Provider=SQLOLEDB;" +  
  "Data Source=(local);Integrated Security=SSPI;Initial Catalog=northwind"))  
{  
OleDbDataAdapter adapter = new OleDbDataAdapter("SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS Orders " +  
  "RELATE CustomerID TO CustomerID)", connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
}  
```  
  
 <span data-ttu-id="6d4ac-178">`Fill` 작업이 완료되면 `DataSet` 에 `Customers` 테이블과 `CustomersOrders`테이블이 포함됩니다. 여기서 `CustomersOrders` 는 장으로 나뉜 열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-178">When the `Fill` operation is complete, the `DataSet` contains two tables: `Customers` and `CustomersOrders`, where `CustomersOrders` represents the chaptered column.</span></span> <span data-ttu-id="6d4ac-179">`Orders` 라는 추가 열이 `Customers` 테이블에 추가되고 `CustomersOrders` 라는 추가 열이 `CustomersOrders` 테이블에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-179">An additional column named `Orders` is added to the `Customers` table, and an additional column named `CustomersOrders` is added to the `CustomersOrders` table.</span></span> <span data-ttu-id="6d4ac-180">`Orders` 테이블의 `Customers` 열은 자동 증분으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-180">The `Orders` column in the `Customers` table is set to auto-increment.</span></span> <span data-ttu-id="6d4ac-181">`DataRelation`를 부모 테이블로 하는 테이블에 추가된 열을 사용하여 `CustomersOrders`라는 `Customers` 이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-181">A `DataRelation`, `CustomersOrders`, is created by using the columns that were added to the tables with `Customers` as the parent table.</span></span> <span data-ttu-id="6d4ac-182">다음 표에서는 몇 가지 샘플 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d4ac-182">The following tables show some sample results.</span></span>  
  
### <a name="tablename-customers"></a><span data-ttu-id="6d4ac-183">TableName: Customers</span><span class="sxs-lookup"><span data-stu-id="6d4ac-183">TableName: Customers</span></span>  
  
|<span data-ttu-id="6d4ac-184">CustomerID</span><span class="sxs-lookup"><span data-stu-id="6d4ac-184">CustomerID</span></span>|<span data-ttu-id="6d4ac-185">CompanyName</span><span class="sxs-lookup"><span data-stu-id="6d4ac-185">CompanyName</span></span>|<span data-ttu-id="6d4ac-186">Orders</span><span class="sxs-lookup"><span data-stu-id="6d4ac-186">Orders</span></span>|  
|----------------|-----------------|------------|  
|<span data-ttu-id="6d4ac-187">ALFKI</span><span class="sxs-lookup"><span data-stu-id="6d4ac-187">ALFKI</span></span>|<span data-ttu-id="6d4ac-188">Alfreds Futterkiste</span><span class="sxs-lookup"><span data-stu-id="6d4ac-188">Alfreds Futterkiste</span></span>|<span data-ttu-id="6d4ac-189">0</span><span class="sxs-lookup"><span data-stu-id="6d4ac-189">0</span></span>|  
|<span data-ttu-id="6d4ac-190">ANATR</span><span class="sxs-lookup"><span data-stu-id="6d4ac-190">ANATR</span></span>|<span data-ttu-id="6d4ac-191">Ana Trujillo Emparedados y helados</span><span class="sxs-lookup"><span data-stu-id="6d4ac-191">Ana Trujillo Emparedados y helados</span></span>|<span data-ttu-id="6d4ac-192">1</span><span class="sxs-lookup"><span data-stu-id="6d4ac-192">1</span></span>|  
  
### <a name="tablename-customersorders"></a><span data-ttu-id="6d4ac-193">TableName: CustomersOrders</span><span class="sxs-lookup"><span data-stu-id="6d4ac-193">TableName: CustomersOrders</span></span>  
  
|<span data-ttu-id="6d4ac-194">CustomerID</span><span class="sxs-lookup"><span data-stu-id="6d4ac-194">CustomerID</span></span>|<span data-ttu-id="6d4ac-195">OrderID</span><span class="sxs-lookup"><span data-stu-id="6d4ac-195">OrderID</span></span>|<span data-ttu-id="6d4ac-196">CustomersOrders</span><span class="sxs-lookup"><span data-stu-id="6d4ac-196">CustomersOrders</span></span>|  
|----------------|-------------|---------------------|  
|<span data-ttu-id="6d4ac-197">ALFKI</span><span class="sxs-lookup"><span data-stu-id="6d4ac-197">ALFKI</span></span>|<span data-ttu-id="6d4ac-198">10643</span><span class="sxs-lookup"><span data-stu-id="6d4ac-198">10643</span></span>|<span data-ttu-id="6d4ac-199">0</span><span class="sxs-lookup"><span data-stu-id="6d4ac-199">0</span></span>|  
|<span data-ttu-id="6d4ac-200">ALFKI</span><span class="sxs-lookup"><span data-stu-id="6d4ac-200">ALFKI</span></span>|<span data-ttu-id="6d4ac-201">10692</span><span class="sxs-lookup"><span data-stu-id="6d4ac-201">10692</span></span>|<span data-ttu-id="6d4ac-202">0</span><span class="sxs-lookup"><span data-stu-id="6d4ac-202">0</span></span>|  
|<span data-ttu-id="6d4ac-203">ANATR</span><span class="sxs-lookup"><span data-stu-id="6d4ac-203">ANATR</span></span>|<span data-ttu-id="6d4ac-204">10308</span><span class="sxs-lookup"><span data-stu-id="6d4ac-204">10308</span></span>|<span data-ttu-id="6d4ac-205">1</span><span class="sxs-lookup"><span data-stu-id="6d4ac-205">1</span></span>|  
|<span data-ttu-id="6d4ac-206">ANATR</span><span class="sxs-lookup"><span data-stu-id="6d4ac-206">ANATR</span></span>|<span data-ttu-id="6d4ac-207">10625</span><span class="sxs-lookup"><span data-stu-id="6d4ac-207">10625</span></span>|<span data-ttu-id="6d4ac-208">1</span><span class="sxs-lookup"><span data-stu-id="6d4ac-208">1</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6d4ac-209">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d4ac-209">See also</span></span>

- [<span data-ttu-id="6d4ac-210">DataAdapters 및 DataReaders</span><span class="sxs-lookup"><span data-stu-id="6d4ac-210">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="6d4ac-211">ADO.NET에서 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="6d4ac-211">Data Type Mappings in ADO.NET</span></span>](data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="6d4ac-212">DbDataAdapter로 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="6d4ac-212">Modifying Data with a DbDataAdapter</span></span>](modifying-data-with-a-dbdataadapter.md)
- [<span data-ttu-id="6d4ac-213">MARS(Multiple Active Result Sets)</span><span class="sxs-lookup"><span data-stu-id="6d4ac-213">Multiple Active Result Sets (MARS)</span></span>](./sql/multiple-active-result-sets-mars.md)
- [<span data-ttu-id="6d4ac-214">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="6d4ac-214">ADO.NET Overview</span></span>](ado-net-overview.md)
