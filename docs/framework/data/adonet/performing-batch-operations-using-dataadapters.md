---
title: DataAdapter를 사용하여 일괄 작업 수행
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e72ed5af-b24f-486c-8429-c8fd2208f844
ms.openlocfilehash: 9dd6abb91b3549e3bc8b4ae84cbb227171512ecb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177425"
---
# <a name="performing-batch-operations-using-dataadapters"></a><span data-ttu-id="aaa95-102">DataAdapter를 사용하여 일괄 작업 수행</span><span class="sxs-lookup"><span data-stu-id="aaa95-102">Performing Batch Operations Using DataAdapters</span></span>

<span data-ttu-id="aaa95-103">ADO.NET의 배치 지원을 사용하면 <xref:System.Data.Common.DataAdapter>를 통해 INSERT, UPDATE 및 DELETE 작업을 한 번에 하나씩 보내지 않고 <xref:System.Data.DataSet> 또는 <xref:System.Data.DataTable>에서 서버로 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-103">Batch support in ADO.NET allows a <xref:System.Data.Common.DataAdapter> to group INSERT, UPDATE, and DELETE operations from a <xref:System.Data.DataSet> or <xref:System.Data.DataTable> to the server, instead of sending one operation at a time.</span></span> <span data-ttu-id="aaa95-104">서버로의 라운드트립 횟수가 줄어들면 일반적으로 성능이 크게 개선됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-104">The reduction in the number of round trips to the server typically results in significant performance gains.</span></span> <span data-ttu-id="aaa95-105">배치 업데이트는 SQL Server(<xref:System.Data.SqlClient>) 및 Oracle(<xref:System.Data.OracleClient>)용 .NET 데이터 공급자에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-105">Batch updates are supported for the .NET data providers for SQL Server (<xref:System.Data.SqlClient>) and Oracle (<xref:System.Data.OracleClient>).</span></span>  
  
 <span data-ttu-id="aaa95-106">이전 버전의 ADO.NET에서는 데이터베이스를 <xref:System.Data.DataSet>의 변경 내용으로 업데이트하는 경우 `Update`의 `DataAdapter` 메서드에서 데이터베이스에 대해 한 번에 한 행씩 업데이트를 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-106">When updating a database with changes from a <xref:System.Data.DataSet> in previous versions of ADO.NET, the `Update` method of a `DataAdapter` performed updates to the database one row at a time.</span></span> <span data-ttu-id="aaa95-107">또한 지정한 <xref:System.Data.DataTable>의 행에서 반복될 때 수정되었는지 여부를 확인하기 위해 각 <xref:System.Data.DataRow>를 검사했습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-107">As it iterated through the rows in the specified <xref:System.Data.DataTable>, it examined each <xref:System.Data.DataRow> to see if it had been modified.</span></span> <span data-ttu-id="aaa95-108">행이 수정된 경우에는 해당 행의 `UpdateCommand` 속성 값에 따라 적절한 `InsertCommand`, `DeleteCommand` 또는 <xref:System.Data.DataRow.RowState%2A>를 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-108">If the row had been modified, it called the appropriate `UpdateCommand`, `InsertCommand`, or `DeleteCommand`, depending on the value of the <xref:System.Data.DataRow.RowState%2A> property for that row.</span></span> <span data-ttu-id="aaa95-109">그리고 행을 업데이트할 때마다 데이터베이스에 대한 네트워크 라운드트립이 수반되었습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-109">Every row update involved a network round-trip to the database.</span></span>  
  
 <span data-ttu-id="aaa95-110">ADO.NET 2.0부터는 <xref:System.Data.Common.DbDataAdapter>가 <xref:System.Data.Common.DbDataAdapter.UpdateBatchSize%2A> 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-110">Starting with ADO.NET 2.0, the <xref:System.Data.Common.DbDataAdapter> exposes an <xref:System.Data.Common.DbDataAdapter.UpdateBatchSize%2A> property.</span></span> <span data-ttu-id="aaa95-111">`UpdateBatchSize`를 양의 정수 값으로 설정하면 데이터베이스에 대한 업데이트가 지정된 크기의 배치로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-111">Setting the `UpdateBatchSize` to a positive integer value causes updates to the database to be sent as batches of the specified size.</span></span> <span data-ttu-id="aaa95-112">예를 들어 `UpdateBatchSize`를 10으로 설정하면 10개의 개별적인 문을 그룹화하여 하나의 배치로 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-112">For example, setting the `UpdateBatchSize` to 10 will group 10 separate statements and submit them as single batch.</span></span> <span data-ttu-id="aaa95-113">`UpdateBatchSize`를 0으로 설정하면 <xref:System.Data.Common.DataAdapter>가 서버에서 처리할 수 있는 최대 배치 크기를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-113">Setting the `UpdateBatchSize` to 0 will cause the <xref:System.Data.Common.DataAdapter> to use the largest batch size that the server can handle.</span></span> <span data-ttu-id="aaa95-114">1로 설정할 경우에는 행이 한 번에 하나씩 전송되므로 배치 업데이트를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-114">Setting it to 1 disables batch updates, as rows are sent one at a time.</span></span>  
  
 <span data-ttu-id="aaa95-115">매우 큰 일괄 처리를 실행 하면 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-115">Executing an extremely large batch could decrease performance.</span></span> <span data-ttu-id="aaa95-116">따라서 애플리케이션을 구현하기 전에 최적의 배치 크기 설정을 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-116">Therefore, you should test for the optimum batch size setting before implementing your application.</span></span>  
  
## <a name="using-the-updatebatchsize-property"></a><span data-ttu-id="aaa95-117">UpdateBatchSize 속성 사용</span><span class="sxs-lookup"><span data-stu-id="aaa95-117">Using the UpdateBatchSize Property</span></span>  

 <span data-ttu-id="aaa95-118">배치 업데이트를 사용할 수 있을 때는 DataAdapter <xref:System.Data.IDbCommand.UpdatedRowSource%2A>, `UpdateCommand` 및 `InsertCommand`의 `DeleteCommand` 속성 값을 <xref:System.Data.UpdateRowSource.None> 또는 <xref:System.Data.UpdateRowSource.OutputParameters>로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-118">When batch updates are enabled, the <xref:System.Data.IDbCommand.UpdatedRowSource%2A> property value of the DataAdapter's `UpdateCommand`, `InsertCommand`, and `DeleteCommand` should be set to <xref:System.Data.UpdateRowSource.None> or <xref:System.Data.UpdateRowSource.OutputParameters>.</span></span> <span data-ttu-id="aaa95-119">배치 업데이트를 수행하는 경우 명령의 <xref:System.Data.IDbCommand.UpdatedRowSource%2A> 속성 값 <xref:System.Data.UpdateRowSource.FirstReturnedRecord> 또는 <xref:System.Data.UpdateRowSource.Both>는 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-119">When performing a batch update, the command's <xref:System.Data.IDbCommand.UpdatedRowSource%2A> property value of <xref:System.Data.UpdateRowSource.FirstReturnedRecord> or <xref:System.Data.UpdateRowSource.Both> is invalid.</span></span>  
  
 <span data-ttu-id="aaa95-120">다음 프로시저에서는 `UpdateBatchSize` 속성을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-120">The following procedure demonstrates the use of the `UpdateBatchSize` property.</span></span> <span data-ttu-id="aaa95-121">이 프로시저는 두 개의 인수, 즉 <xref:System.Data.DataSet> **Production category** 테이블의 **제품 categoryid** 및 **Name** 필드를 나타내는 열이 있는 개체와 일괄 처리 크기 (일괄 처리의 행 수)를 나타내는 정수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-121">The procedure takes two arguments, a <xref:System.Data.DataSet> object that has columns representing the **ProductCategoryID** and **Name** fields in the **Production.ProductCategory** table, and an integer representing the batch size (the number of rows in the batch).</span></span> <span data-ttu-id="aaa95-122">이 코드에서는 <xref:System.Data.SqlClient.SqlDataAdapter>, <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A> 및 <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> 속성을 설정하여 새 <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-122">The code creates a new <xref:System.Data.SqlClient.SqlDataAdapter> object, setting its <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>, and <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> properties.</span></span> <span data-ttu-id="aaa95-123">또한 <xref:System.Data.DataSet> 개체에 수정된 행이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-123">The code assumes that the <xref:System.Data.DataSet> object has modified rows.</span></span> <span data-ttu-id="aaa95-124">그리고 `UpdateBatchSize` 속성을 설정한 다음 업데이트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-124">It sets the `UpdateBatchSize` property and executes the update.</span></span>  
  
```vb  
Public Sub BatchUpdate( _  
  ByVal dataTable As DataTable, ByVal batchSize As Int32)  
    ' Assumes GetConnectionString() returns a valid connection string.  
    Dim connectionString As String = GetConnectionString()  
  
    ' Connect to the AdventureWorks database.  
    Using connection As New SqlConnection(connectionString)  
        ' Create a SqlDataAdapter.  
        Dim adapter As New SqlDataAdapter()  
  
        'Set the UPDATE command and parameters.  
        adapter.UpdateCommand = New SqlCommand( _  
          "UPDATE Production.ProductCategory SET " _  
          & "Name=@Name WHERE ProductCategoryID=@ProdCatID;", _  
          connection)  
        adapter.UpdateCommand.Parameters.Add("@Name", _  
          SqlDbType.NVarChar, 50, "Name")  
        adapter.UpdateCommand.Parameters.Add("@ProdCatID",  _  
          SqlDbType.Int, 4, " ProductCategoryID ")  
        adapter.UpdateCommand.UpdatedRowSource = _  
          UpdateRowSource.None  
  
        'Set the INSERT command and parameter.  
        adapter.InsertCommand = New SqlCommand( _  
          "INSERT INTO Production.ProductCategory (Name) VALUES (@Name);", _  
  connection)  
        adapter.InsertCommand.Parameters.Add("@Name", _  
          SqlDbType.NVarChar, 50, "Name")  
        adapter.InsertCommand.UpdatedRowSource = _  
          UpdateRowSource.None  
  
        'Set the DELETE command and parameter.  
        adapter.DeleteCommand = New SqlCommand( _  
          "DELETE FROM Production.ProductCategory " _  
          & "WHERE ProductCategoryID=@ProdCatID;", connection)  
        adapter.DeleteCommand.Parameters.Add("@ProdCatID", _  
           SqlDbType.Int, 4, " ProductCategoryID ")  
        adapter.DeleteCommand.UpdatedRowSource = UpdateRowSource.None  
  
        ' Set the batch size.  
        adapter.UpdateBatchSize = batchSize  
  
        ' Execute the update.  
        adapter.Update(dataTable)  
    End Using  
End Sub  
```  
  
```csharp  
public static void BatchUpdate(DataTable dataTable,Int32 batchSize)  
{  
    // Assumes GetConnectionString() returns a valid connection string.  
    string connectionString = GetConnectionString();  
  
    // Connect to the AdventureWorks database.  
    using (SqlConnection connection = new
      SqlConnection(connectionString))  
    {  
  
        // Create a SqlDataAdapter.  
        SqlDataAdapter adapter = new SqlDataAdapter();  
  
        // Set the UPDATE command and parameters.  
        adapter.UpdateCommand = new SqlCommand(  
            "UPDATE Production.ProductCategory SET "  
            + "Name=@Name WHERE ProductCategoryID=@ProdCatID;",
            connection);  
        adapter.UpdateCommand.Parameters.Add("@Name",
           SqlDbType.NVarChar, 50, "Name");  
        adapter.UpdateCommand.Parameters.Add("@ProdCatID",
           SqlDbType.Int, 4, "ProductCategoryID");  
         adapter.UpdateCommand.UpdatedRowSource = UpdateRowSource.None;  
  
        // Set the INSERT command and parameter.  
        adapter.InsertCommand = new SqlCommand(  
            "INSERT INTO Production.ProductCategory (Name) VALUES (@Name);",
            connection);  
        adapter.InsertCommand.Parameters.Add("@Name",
          SqlDbType.NVarChar, 50, "Name");  
        adapter.InsertCommand.UpdatedRowSource = UpdateRowSource.None;  
  
        // Set the DELETE command and parameter.  
        adapter.DeleteCommand = new SqlCommand(  
            "DELETE FROM Production.ProductCategory "  
            + "WHERE ProductCategoryID=@ProdCatID;", connection);  
        adapter.DeleteCommand.Parameters.Add("@ProdCatID",
          SqlDbType.Int, 4, "ProductCategoryID");  
        adapter.DeleteCommand.UpdatedRowSource = UpdateRowSource.None;  
  
        // Set the batch size.  
        adapter.UpdateBatchSize = batchSize;  
  
        // Execute the update.  
        adapter.Update(dataTable);  
    }  
}  
```  
  
## <a name="handling-batch-update-related-events-and-errors"></a><span data-ttu-id="aaa95-125">배치 업데이트 관련 이벤트 및 오류 처리</span><span class="sxs-lookup"><span data-stu-id="aaa95-125">Handling Batch Update-Related Events and Errors</span></span>  

 <span data-ttu-id="aaa95-126">**DataAdapter** 에는 두 가지 업데이트 관련 이벤트 인 **RowUpdating** 및 **RowUpdated**이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-126">The **DataAdapter** has two update-related events: **RowUpdating** and **RowUpdated**.</span></span> <span data-ttu-id="aaa95-127">이전 버전의 ADO.NET에서 일괄 처리가 비활성화되어 있는 경우 각 이벤트는 처리되는 각 행마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-127">In previous versions of ADO.NET, when batch processing is disabled, each of these events is generated once for each row processed.</span></span> <span data-ttu-id="aaa95-128">업데이트를 수행 하기 전에 **RowUpdating** 이 생성 되 고 데이터베이스 업데이트가 완료 된 후 **RowUpdated** 이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-128">**RowUpdating** is generated before the update occurs, and **RowUpdated** is generated after the database update has been completed.</span></span>  
  
### <a name="event-behavior-changes-with-batch-updates"></a><span data-ttu-id="aaa95-129">배치 업데이트에 따른 이벤트 동작 변경</span><span class="sxs-lookup"><span data-stu-id="aaa95-129">Event Behavior Changes with Batch Updates</span></span>  

 <span data-ttu-id="aaa95-130">일괄 처리가 활성화되면 한 번의 데이터베이스 동작으로 여러 개의 행이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-130">When batch processing is enabled, multiple rows are updated in a single database operation.</span></span> <span data-ttu-id="aaa95-131">따라서 `RowUpdated` 이벤트는 배치마다 한 번씩만 발생하지만 `RowUpdating` 이벤트는 행이 처리될 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-131">Therefore, only one `RowUpdated` event occurs for each batch, whereas the `RowUpdating` event occurs for each row processed.</span></span> <span data-ttu-id="aaa95-132">일괄 처리가 비활성화되면 일대일 인터리빙으로 두 개의 이벤트가 발생합니다. 이 경우 `RowUpdating` 이벤트 하나와 `RowUpdated` 이벤트 하나가 한 행에 대해 발생한 후 모든 행이 처리될 때까지 `RowUpdating` 및 `RowUpdated` 이벤트가 다음 행에 대해 하나씩 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-132">When batch processing is disabled, the two events are fired with one-to-one interleaving, where one `RowUpdating` event and one `RowUpdated` event fire for a row, and then one `RowUpdating` and one `RowUpdated` event fire for the next row, until all of the rows are processed.</span></span>  
  
### <a name="accessing-updated-rows"></a><span data-ttu-id="aaa95-133">업데이트된 행 액세스</span><span class="sxs-lookup"><span data-stu-id="aaa95-133">Accessing Updated Rows</span></span>  

 <span data-ttu-id="aaa95-134">일괄 처리가 비활성화되면 <xref:System.Data.Common.RowUpdatedEventArgs.Row%2A> 클래스의 <xref:System.Data.Common.RowUpdatedEventArgs> 속성을 사용하여 업데이트되는 행에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-134">When batch processing is disabled, the row being updated can be accessed using the <xref:System.Data.Common.RowUpdatedEventArgs.Row%2A> property of the <xref:System.Data.Common.RowUpdatedEventArgs> class.</span></span>  
  
 <span data-ttu-id="aaa95-135">일괄 처리가 활성화되면 여러 행에 대해 하나의 `RowUpdated` 이벤트가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-135">When batch processing is enabled, a single `RowUpdated` event is generated for multiple rows.</span></span> <span data-ttu-id="aaa95-136">따라서 각 행에 대한 `Row` 속성 값은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-136">Therefore, the value of the `Row` property for each row is null.</span></span> <span data-ttu-id="aaa95-137">`RowUpdating` 이벤트는 계속해서 각 행에 대해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-137">`RowUpdating` events are still generated for each row.</span></span> <span data-ttu-id="aaa95-138"><xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A> 클래스의 <xref:System.Data.Common.RowUpdatedEventArgs> 메서드를 사용하면 행에 대한 참조를 배열에 복사하여 처리된 행에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-138">The <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A> method of the <xref:System.Data.Common.RowUpdatedEventArgs> class allows you to access the processed rows by copying references to the rows into an array.</span></span> <span data-ttu-id="aaa95-139">처리 중인 행이 없으면 `CopyToRows`에서 <xref:System.ArgumentNullException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-139">If no rows are being processed, `CopyToRows` throws an <xref:System.ArgumentNullException>.</span></span> <span data-ttu-id="aaa95-140"><xref:System.Data.Common.RowUpdatedEventArgs.RowCount%2A> 메서드를 호출하기 전에 <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A> 속성을 사용하여 처리된 행 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-140">Use the <xref:System.Data.Common.RowUpdatedEventArgs.RowCount%2A> property to return the number of rows processed before calling the <xref:System.Data.Common.RowUpdatedEventArgs.CopyToRows%2A> method.</span></span>  
  
### <a name="handling-data-errors"></a><span data-ttu-id="aaa95-141">데이터 오류 처리</span><span class="sxs-lookup"><span data-stu-id="aaa95-141">Handling Data Errors</span></span>  

 <span data-ttu-id="aaa95-142">배치를 실행하면 각각의 개별 문을 실행하는 것과 동일한 효과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-142">Batch execution has the same effect as the execution of each individual statement.</span></span> <span data-ttu-id="aaa95-143">문은 배치에 추가된 순서대로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-143">Statements are executed in the order that the statements were added to the batch.</span></span> <span data-ttu-id="aaa95-144">오류는 배치 모드가 비활성화되어 있는 상태와 동일하게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-144">Errors are handled the same way in batch mode as they are when batch mode is disabled.</span></span> <span data-ttu-id="aaa95-145">행은 각각 개별적으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-145">Each row is processed separately.</span></span> <span data-ttu-id="aaa95-146">데이터베이스에서 성공적으로 처리된 행만 <xref:System.Data.DataRow> 내의 해당 <xref:System.Data.DataTable>에서 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-146">Only rows that have been successfully processed in the database will be updated in the corresponding <xref:System.Data.DataRow> within the <xref:System.Data.DataTable>.</span></span>  
  
 <span data-ttu-id="aaa95-147">데이터 공급자 및 백 엔드 데이터베이스 서버는 배치 실행에 지원되는 SQL 구문을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-147">The data provider and the back-end database server determine which SQL constructs are supported for batch execution.</span></span> <span data-ttu-id="aaa95-148">실행을 위해 지원되지 않는 문을 전송하면 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-148">An exception may be thrown if a non-supported statement is submitted for execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa95-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aaa95-149">See also</span></span>

- [<span data-ttu-id="aaa95-150">DataAdapters 및 DataReaders</span><span class="sxs-lookup"><span data-stu-id="aaa95-150">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="aaa95-151">DataAdapters로 데이터 원본 업데이트</span><span class="sxs-lookup"><span data-stu-id="aaa95-151">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="aaa95-152">DataAdapter 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="aaa95-152">Handling DataAdapter Events</span></span>](handling-dataadapter-events.md)
- [<span data-ttu-id="aaa95-153">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="aaa95-153">ADO.NET Overview</span></span>](ado-net-overview.md)
