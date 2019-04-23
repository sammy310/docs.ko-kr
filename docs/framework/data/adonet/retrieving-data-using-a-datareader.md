---
title: DataReader를 사용하여 데이터 검색
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 8063f239123ec1a2f2650adf9d76f7ceaaa50673
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128689"
---
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="27580-102">DataReader를 사용 하 여 데이터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-102">Retrieve data using a DataReader</span></span>
<span data-ttu-id="27580-103">사용 하 여 데이터를 검색 하는 **DataReader**의 인스턴스를 만듭니다 합니다 **명령** 개체를 만든 다음을 **DataReader** 호출 하 여 **Command.ExecuteReader**  데이터 원본에서 행을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-103">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="27580-104">합니다 **DataReader** 절차적 논리 없이 효율적으로 데이터 소스에서 결과 순차적으로 처리할 수 있도록 데이터를 버퍼링 되지 않은 스트림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-104">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="27580-105">합니다 **DataReader** 데이터가 메모리에 캐시 되지 않기 때문에 많은 양의 데이터를 검색 하는 경우 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-105">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="27580-106">다음 예제를 사용 하는 **DataReader**여기서 `reader` 올바른 DataReader를 나타내는 및 `command` 올바른 Command 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="27580-106">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="27580-107">사용 된 **DataReader.Read** 메서드는 쿼리 결과에서 행을 가져오려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-107">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="27580-108">이름 또는 열의 서 수 번호를 전달 하 여 반환된 된 행의 각 열에 액세스할 수 있습니다 합니다 **DataReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-108">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="27580-109">최상의 성능을 위해 합니다 **DataReader** 일련의 네이티브 데이터 형식으로 열 값에 액세스할 수 있도록 하는 메서드를 제공 (**GetDateTime**, **GetDouble**하십시오 **GetGuid**를 **GetInt32**등).</span><span class="sxs-lookup"><span data-stu-id="27580-109">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="27580-110">데이터 공급자별으로 형식화 된 접근자 메서드 목록을 **DataReaders**를 참조 하십시오 <xref:System.Data.OleDb.OleDbDataReader> 및 <xref:System.Data.SqlClient.SqlDataReader>합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-110">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="27580-111">기본 데이터를 알고 있는 경우에 형식화 된 접근자 메서드를 사용 하 여 형식 열 값을 검색할 때 필요한 형식 변환의 크기를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="27580-111">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="27580-112">다음 예제에서는 반복을 **DataReader** 개체 및 각 행에서 두 개의 열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-112">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="27580-113">DataReader 닫기</span><span class="sxs-lookup"><span data-stu-id="27580-113">Closing the DataReader</span></span>  
 <span data-ttu-id="27580-114">항상 호출 합니다 **닫기** 메서드를 사용 하 여 완료 한 후 합니다 **DataReader** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="27580-114">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="27580-115">경우에 **명령** 출력이 포함 값까지 사용할 수 없는 매개 변수 또는 반환 값을 **DataReader** 닫혀 합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-115">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="27580-116">하는 동안를 **DataReader** 열려 있는 경우 합니다 **연결** 에서 단독으로 사용 중인 **DataReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-116">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="27580-117">에 대해 어떤 명령도 실행할 수 없습니다는 **연결**, 등 다른 **DataReader**, 원래 될 때까지 **DataReader** 닫혀 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27580-117">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27580-118">호출 하지 마세요 **닫기** 또는 **Dispose** 에 **연결**, **DataReader**, 또는 다른 관리 개체에는 **Finalize**  클래스의 메서드.</span><span class="sxs-lookup"><span data-stu-id="27580-118">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="27580-119">종료자에서는 클래스에 직접 속한 관리되지 않는 리소스만 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-119">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="27580-120">클래스는 관리 되지 않는 리소스를 소유 하지 않습니다, 경우 포함 되지 않습니다는 **Finalize** 클래스 정의에 메서드.</span><span class="sxs-lookup"><span data-stu-id="27580-120">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="27580-121">자세한 내용은 [가비지 수집](../../../../docs/standard/garbage-collection/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-121">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="27580-122">NextResult를 사용 하 여 집합 여러 결과 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-122">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="27580-123">경우는 **DataReader** 호출 여러 결과 집합을 반환 합니다 **NextResult** 결과 반복 하는 메서드를 순차적으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-123">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="27580-124">다음 예제에서는 <xref:System.Data.SqlClient.SqlDataReader>가 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 메서드를 사용하여 두 가지 SELECT 문 결과를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="27580-124">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="27580-125">DataReader에서 스키마 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="27580-125">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="27580-126">하는 동안를 **DataReader** 가 열기를 가져오면 현재 결과 사용 하 여 집합에 대 한 스키마 정보를 **GetSchemaTable** 메서드.</span><span class="sxs-lookup"><span data-stu-id="27580-126">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="27580-127">**GetSchemaTable** 반환을 <xref:System.Data.DataTable> 현재 결과 집합에 대 한 스키마 정보를 포함 하는 행과 열으로 채워진 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="27580-127">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="27580-128">합니다 **DataTable** 결과 집합의 각 열에 대해 하나의 행을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-128">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="27580-129">스키마 테이블의 각 열에 반환 된 열의 속성에 매핑됩니다 있는 결과의 행을 설정 합니다 **ColumnName** 속성의 이름이 며 열의 값은 속성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="27580-129">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="27580-130">다음 예제에 대 한 스키마 정보를 씁니다 **DataReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-130">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="27580-131">OLE DB 장 사용</span><span class="sxs-lookup"><span data-stu-id="27580-131">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="27580-132">계층적 행 집합 또는 장 (OLE DB 형식 **DBTYPE_HCHAPTER**, ADO 형식 **adChapter**)를 사용 하 여 검색할 수는 <xref:System.Data.OleDb.OleDbDataReader>합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-132">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="27580-133">장을 포함 하는 쿼리로 반환 될 때를 **DataReader**의 열으로 반환 되는 **DataReader** 으로 노출 되는 **DataReader** 개체.</span><span class="sxs-lookup"><span data-stu-id="27580-133">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="27580-134">ADO.NET **데이터 집합** 테이블 간의 부모-자식 관계를 사용 하 여 계층적 행 집합을 나타내는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27580-134">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="27580-135">자세한 내용은 [Dataset, Datatable 및 Dataview](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-135">For more information, see [DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="27580-136">다음 코드 예제에서는 MSDataShape 공급자를 사용하여 고객 목록에 있는 각 고객의 주문에 대해 장 열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-136">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" &
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")

    Using custCMD As OleDbCommand = New OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " &
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " &
        "RELATE CustomerID TO CustomerID)", connection)

        connection.Open()

        Using custReader As OleDbDataReader = custCMD.ExecuteReader()

            Do While custReader.Read()
                Console.WriteLine("Orders for " & custReader.GetString(1))
                ' custReader.GetString(1) = CompanyName  

                Using orderReader As OleDbDataReader = custReader.GetValue(2)
                    ' custReader.GetValue(2) = Orders chapter as DataReader  

                    Do While orderReader.Read()
                        Console.WriteLine(vbTab & orderReader.GetInt32(1))
                        ' orderReader.GetInt32(1) = OrderID  
                    Loop
                    orderReader.Close()
                End Using
            Loop
            ' Make sure to always close readers and connections.  
            custReader.Close()
        End Using
    End Using
End Using
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" +
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"))
{
    using (OleDbCommand custCMD = new OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +
        "RELATE CustomerID TO CustomerID)", connection))
    {
        connection.Open();

        using (OleDbDataReader custReader = custCMD.ExecuteReader())
        {

            while (custReader.Read())
            {
                Console.WriteLine("Orders for " + custReader.GetString(1));
                // custReader.GetString(1) = CompanyName  

                using (OleDbDataReader orderReader = (OleDbDataReader)custReader.GetValue(2))
                {
                    // custReader.GetValue(2) = Orders chapter as DataReader  

                    while (orderReader.Read())
                        Console.WriteLine("\t" + orderReader.GetInt32(1));
                    // orderReader.GetInt32(1) = OrderID  
                    orderReader.Close();
                }
            }
            // Make sure to always close readers and connections.  
            custReader.Close();
        }
    }
}
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="27580-137">Oracle REF Cursor를 사용 하 여 결과 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-137">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="27580-138">.NET Framework Data Provider for Oracle을 사용하면 Oracle REF CURSOR를 사용하여 쿼리 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27580-138">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="27580-139">Oracle REF CURSOR는 <xref:System.Data.OracleClient.OracleDataReader>로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="27580-139">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="27580-140">검색할 수 있습니다는 <xref:System.Data.OracleClient.OracleDataReader> 를 사용 하 여 Oracle REF CURSOR를 나타내는 개체를 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="27580-140">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="27580-141">지정할 수도 있습니다는 <xref:System.Data.OracleClient.OracleCommand> 으로 하나 이상의 Oracle REF Cursor를 반환 하는 합니다 **SelectCommand** 에 대 한는 <xref:System.Data.OracleClient.OracleDataAdapter> 채우는 데는 <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="27580-141">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="27580-142">Oracle 데이터 원본에서 반환 하는 REF CURSOR에 액세스 하려면 만듭니다는 <xref:System.Data.OracleClient.OracleCommand> 쿼리에 대 한 REF CURSOR를 참조 하는 출력 매개 변수를 추가 합니다 <xref:System.Data.OracleClient.OracleCommand.Parameters> 의 컬렉션에 <xref:System.Data.OracleClient.OracleCommand>합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-142">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="27580-143">매개 변수 이름은 쿼리의 REF CURSOR 매개 변수 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="27580-144">매개 변수의 형식을 설정 <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-144">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="27580-145"><xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> 메서드의 하 <xref:System.Data.OracleClient.OracleCommand> 반환는 <xref:System.Data.OracleClient.OracleDataReader> REF CURSOR에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-145">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="27580-146">경우에 <xref:System.Data.OracleClient.OracleCommand> 여러 REF CURSOR를 반환 합니다. 여러 출력 매개 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-146">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="27580-147">호출 하 여 서로 다른 REF Cursor에 액세스할 수 있습니다는 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="27580-147">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="27580-148">에 대 한 호출 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> 반환을 <xref:System.Data.OracleClient.OracleDataReader> 하면 첫 REF CURSOR를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-148">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="27580-149">호출할 수 있습니다는 <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> REF Cursor에 액세스 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="27580-149">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="27580-150">하지만 매개 변수 프로그램 <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> 이름별로 컬렉션 일치 REF CURSOR 출력 매개 변수를 <xref:System.Data.OracleClient.OracleDataReader> 에 추가 된 순서 대로 액세스는 <xref:System.Data.OracleClient.OracleCommand.Parameters> 컬렉션.</span><span class="sxs-lookup"><span data-stu-id="27580-150">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="27580-151">예를 들어, 다음과 같은 Oracle 패키지 및 패키지 본문이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27580-151">For example, consider the following Oracle package and package body.</span></span>  
  
```sql
CREATE OR REPLACE PACKAGE CURSPKG AS   
  TYPE T_CURSOR IS REF CURSOR;   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR);   
END CURSPKG;  
  
CREATE OR REPLACE PACKAGE BODY CURSPKG AS   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR)   
  IS   
  BEGIN   
    OPEN EMPCURSOR FOR SELECT * FROM DEMO.EMPLOYEE;   
    OPEN DEPTCURSOR FOR SELECT * FROM DEMO.DEPARTMENT;   
  END OPEN_TWO_CURSORS;   
END CURSPKG;   
```  
  
 <span data-ttu-id="27580-152">다음 코드는 <xref:System.Data.OracleClient.OracleCommand> 형식의 두 매개 변수를 추가 하 여 이전 Oracle 패키지에서 REF Cursor를 반환 하는 <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> 에 <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="27580-152">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
```vb  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
```  
  
```csharp  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
```  
  
 <span data-ttu-id="27580-153">다음 코드를 사용 하 여 이전 명령 결과 반환 합니다 <xref:System.Data.OracleClient.OracleDataReader.Read> 및 <xref:System.Data.OracleClient.OracleDataReader.NextResult> 의 메서드는 <xref:System.Data.OracleClient.OracleDataReader>합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-153">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="27580-154">REF CURSOR 매개 변수가 순서대로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="27580-154">The REF CURSOR parameters are returned in order.</span></span>  
  
```vb  
oraConn.Open()  
  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.CommandType = CommandType.StoredProcedure  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
  
Dim reader As OracleDataReader = cursCmd.ExecuteReader()  
  
Console.WriteLine(vbCrLf & "Emp ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2))  
Loop  
  
reader.NextResult()  
  
Console.WriteLine(vbCrLf & "Dept ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}", reader.GetOracleNumber(0), reader.GetString(1))  
Loop  
' Make sure to always close readers and connections.  
reader.Close()  
oraConn.Close()  
```  
  
```csharp  
oraConn.Open();  
  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.CommandType = CommandType.StoredProcedure;  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
  
OracleDataReader reader = cursCmd.ExecuteReader();  
  
Console.WriteLine("\nEmp ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2));  
  
reader.NextResult();  
  
Console.WriteLine("\nDept ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}", reader.GetOracleNumber(0), reader.GetString(1));  
// Make sure to always close readers and connections.  
reader.Close();  
oraConn.Close();  
```  
  
 <span data-ttu-id="27580-155">다음 예제에서는 명령을 사용 하 여 이전 채우기는 <xref:System.Data.DataSet> Oracle 패키지의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="27580-155">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
```vb  
Dim ds As DataSet = New DataSet()  
  
Dim adapter As OracleDataAdapter = New OracleDataAdapter(cursCmd)  
adapter.TableMappings.Add("Table", "Employees")  
adapter.TableMappings.Add("Table1", "Departments")  
  
adapter.Fill(ds)  
```  
  
```csharp  
DataSet ds = new DataSet();  
  
OracleDataAdapter adapter = new OracleDataAdapter(cursCmd);  
adapter.TableMappings.Add("Table", "Employees");  
adapter.TableMappings.Add("Table1", "Departments");  
  
adapter.Fill(ds);  
```

> [!NOTE]
>  <span data-ttu-id="27580-156">않으려면를 **OverflowException**, 모든 변환할 Oracle NUMBER 형식 유효한.NET Framework 형식으로 값을 저장 하기 전에 처리 하는 것이 좋습니다는 <xref:System.Data.DataRow>합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="27580-157">사용할 수는 <xref:System.Data.Common.DataAdapter.FillError> 여부를 확인 하는 이벤트를 **OverflowException** 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27580-157">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="27580-158">에 대 한 자세한 합니다 <xref:System.Data.Common.DataAdapter.FillError> 이벤트를 참조 하세요 [DataAdapter 이벤트 처리](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27580-158">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27580-159">참고자료</span><span class="sxs-lookup"><span data-stu-id="27580-159">See also</span></span>

- [<span data-ttu-id="27580-160">DataAdapter 및 DataReader</span><span class="sxs-lookup"><span data-stu-id="27580-160">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="27580-161">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="27580-161">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="27580-162">데이터베이스 스키마 정보 검색</span><span class="sxs-lookup"><span data-stu-id="27580-162">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [<span data-ttu-id="27580-163">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="27580-163">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
