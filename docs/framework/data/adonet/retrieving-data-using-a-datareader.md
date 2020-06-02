---
title: DataReader를 사용하여 데이터 검색
description: 이 샘플 코드를 사용 하 여 ADO.NET에서 DataReader를 사용 하 여 데이터를 검색 하는 방법을 알아봅니다. DataReader는 버퍼링 되지 않은 데이터 스트림을 제공 합니다.
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 6e5161cc325bf0379bb9241b99c473c539ad1081
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286600"
---
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="4c9d3-104">DataReader를 사용한 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="4c9d3-104">Retrieve data using a DataReader</span></span>
<span data-ttu-id="4c9d3-105">**DataReader**를 사용 하 여 데이터를 검색 하려면 **command** 개체의 인스턴스를 만든 다음 **ExecuteReader** 를 호출 하 여 데이터 원본에서 행을 검색 하 여 **DataReader** 를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-105">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="4c9d3-106">**DataReader** 는 데이터 원본에서 순차적으로 결과를 효율적으로 처리 하는 절차적 논리를 허용 하는 버퍼링 되지 않은 데이터 스트림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-106">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="4c9d3-107">**DataReader** 는 데이터가 메모리에 캐시 되지 않기 때문에 대량의 데이터를 검색 하는 경우에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-107">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="4c9d3-108">다음 예제에서는 **datareader**를 사용 하는 방법을 보여 줍니다. 여기서은 `reader` 유효한 datareader를 나타내고는 `command` 유효한 명령 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-108">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="4c9d3-109">**DataReader** 메서드를 사용 하 여 쿼리 결과에서 행을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-109">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="4c9d3-110">열의 이름 또는 서 수를 **DataReader**에 전달 하 여 반환 된 행의 각 열에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-110">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="4c9d3-111">그러나 최상의 성능을 위해 **DataReader** 는 네이티브 데이터 형식 (**getdatetime**, **getdatetime**, **getdatetime**, **GetInt32**등)의 열 값에 액세스할 수 있도록 하는 일련의 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-111">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="4c9d3-112">데이터 공급자별 데이터 **판독기**의 형식화 된 접근자 메서드 목록은 및를 참조 하십시오 <xref:System.Data.OleDb.OleDbDataReader> <xref:System.Data.SqlClient.SqlDataReader> .</span><span class="sxs-lookup"><span data-stu-id="4c9d3-112">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="4c9d3-113">기본 데이터 형식을 알고 있는 경우 형식화 된 접근자 메서드를 사용 하면 열 값을 검색할 때 필요한 형식 변환의 양이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-113">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="4c9d3-114">다음 예에서는 **DataReader** 개체를 반복 하 고 각 행에서 두 개의 열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-114">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="4c9d3-115">DataReader 닫기</span><span class="sxs-lookup"><span data-stu-id="4c9d3-115">Closing the DataReader</span></span>  
 <span data-ttu-id="4c9d3-116">**DataReader** 개체 사용을 완료 한 후에는 항상 **Close** 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-116">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="4c9d3-117">**명령** 에 출력 매개 변수 또는 반환 값이 포함 된 경우 **DataReader** 를 닫을 때까지 해당 값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-117">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="4c9d3-118">**Datareader** 가 열려 있는 동안에는 해당 **datareader**에서 단독으로 **연결** 을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-118">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="4c9d3-119">원본 **datareader** 가 닫힐 때까지 다른 **datareader**만들기를 포함 하 여 **연결**에 대 한 명령을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-119">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c9d3-120">클래스의 **Finalize** 메서드에서 **Connection**, **DataReader**또는 기타 관리 되는 개체에 대해 **Close** 또는 **Dispose** 를 호출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-120">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="4c9d3-121">종료자에서는 클래스에 직접 속한 관리되지 않는 리소스만 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-121">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="4c9d3-122">클래스에 관리 되지 않는 리소스가 없는 경우 클래스 정의에 **Finalize** 메서드를 포함 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-122">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="4c9d3-123">자세한 내용은 [가비지 수집](../../../standard/garbage-collection/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-123">For more information, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="4c9d3-124">NextResult를 사용 하 여 여러 결과 집합 검색</span><span class="sxs-lookup"><span data-stu-id="4c9d3-124">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="4c9d3-125">**DataReader** 에서 여러 결과 집합을 반환 하는 경우 **nextresult** 메서드를 호출 하 여 결과 집합을 순차적으로 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-125">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="4c9d3-126">다음 예제에서는 <xref:System.Data.SqlClient.SqlDataReader>가 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 메서드를 사용하여 두 가지 SELECT 문 결과를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-126">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="4c9d3-127">DataReader에서 스키마 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="4c9d3-127">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="4c9d3-128">**DataReader** 가 열려 있는 동안에는 **getschematable** 수 있는 메서드를 사용 하 여 현재 결과 집합에 대 한 스키마 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-128">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="4c9d3-129">**Getschematable** <xref:System.Data.DataTable> 은 현재 결과 집합에 대 한 스키마 정보를 포함 하는 행과 열로 채워진 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-129">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="4c9d3-130">**DataTable** 은 결과 집합의 각 열에 대해 하나의 행을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-130">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="4c9d3-131">스키마 테이블의 각 열은 결과 집합의 행에 반환 된 열의 속성에 매핑됩니다. 여기서 **ColumnName** 은 속성의 이름이 고 열 값은 속성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-131">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="4c9d3-132">다음 예제에서는 **DataReader**의 스키마 정보를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-132">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="4c9d3-133">OLE DB 챕터 사용</span><span class="sxs-lookup"><span data-stu-id="4c9d3-133">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="4c9d3-134">계층적 행 집합 또는 챕터 (OLE DB 형식 **DBTYPE_HCHAPTER**, ADO 유형 **adchapter**)는를 사용 하 여 검색할 수 있습니다 <xref:System.Data.OleDb.OleDbDataReader> .</span><span class="sxs-lookup"><span data-stu-id="4c9d3-134">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="4c9d3-135">챕터를 포함 하는 쿼리가 **datareader**로 반환 되는 경우이 장은 **datareader** 에서 열로 반환 되 고 **datareader** 개체로 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-135">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="4c9d3-136">ADO.NET **데이터 집합** 을 사용 하 여 테이블 간 부모-자식 관계를 사용 하 여 계층적 행 집합을 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-136">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="4c9d3-137">자세한 내용은 [데이터 집합, datatable 및 DataViews](./dataset-datatable-dataview/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-137">For more information, see [DataSets, DataTables, and DataViews](./dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="4c9d3-138">다음 코드 예제에서는 MSDataShape 공급자를 사용하여 고객 목록에 있는 각 고객의 주문에 대해 장 열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-138">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="4c9d3-139">Oracle REF Cursor를 사용 하 여 결과 반환</span><span class="sxs-lookup"><span data-stu-id="4c9d3-139">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="4c9d3-140">.NET Framework Data Provider for Oracle을 사용하면 Oracle REF CURSOR를 사용하여 쿼리 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-140">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="4c9d3-141">Oracle REF CURSOR는 <xref:System.Data.OracleClient.OracleDataReader>로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-141">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="4c9d3-142"><xref:System.Data.OracleClient.OracleDataReader>메서드를 사용 하 여 ORACLE REF CURSOR를 나타내는 개체를 검색할 수 있습니다 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> .</span><span class="sxs-lookup"><span data-stu-id="4c9d3-142">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="4c9d3-143"><xref:System.Data.OracleClient.OracleCommand>하나 이상의 ORACLE REF cursor를 **SelectCommand** <xref:System.Data.OracleClient.OracleDataAdapter> 를 채우는 데 사용 되는의 SelectCommand로 반환 하는를 지정할 수도 있습니다 <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="4c9d3-143">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="4c9d3-144">Oracle 데이터 원본에서 반환 된 REF 커서에 액세스 하려면 <xref:System.Data.OracleClient.OracleCommand> 쿼리에 대해를 만들고 REF 커서를 참조 하는 출력 매개 변수를의 컬렉션에 추가 <xref:System.Data.OracleClient.OracleCommand.Parameters> <xref:System.Data.OracleClient.OracleCommand> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-144">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="4c9d3-145">매개 변수 이름은 쿼리의 REF CURSOR 매개 변수 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-145">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="4c9d3-146">매개 변수의 형식을로 설정 <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-146">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4c9d3-147"><xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType>의 메서드는 <xref:System.Data.OracleClient.OracleCommand> <xref:System.Data.OracleClient.OracleDataReader> REF 커서에 대해를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-147">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="4c9d3-148">에서 <xref:System.Data.OracleClient.OracleCommand> 여러 REF cursor를 반환 하는 경우 여러 출력 매개 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-148">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="4c9d3-149">메서드를 호출 하 여 다른 REF Cursor에 액세스할 수 있습니다 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4c9d3-149">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4c9d3-150">를 호출 하면 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> <xref:System.Data.OracleClient.OracleDataReader> 첫 번째 REF 커서를 참조 하는이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-150">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="4c9d3-151">그런 다음 메서드를 호출 <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> 하 여 후속 REF 커서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-151">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="4c9d3-152">컬렉션의 매개 변수가 <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> 이름으로 REF CURSOR 출력 매개 변수와 일치 하더라도는 <xref:System.Data.OracleClient.OracleDataReader> 컬렉션에 추가 된 순서 대로 해당 매개 변수를 액세스 합니다 <xref:System.Data.OracleClient.OracleCommand.Parameters> .</span><span class="sxs-lookup"><span data-stu-id="4c9d3-152">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="4c9d3-153">예를 들어, 다음과 같은 Oracle 패키지 및 패키지 본문이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-153">For example, consider the following Oracle package and package body.</span></span>  
  
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
  
 <span data-ttu-id="4c9d3-154">다음 코드에서는 <xref:System.Data.OracleClient.OracleCommand> 컬렉션에 형식의 매개 변수 두 개를 추가 하 여 이전 Oracle 패키지에서 REF cursor를 반환 하는를 만듭니다 <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4c9d3-154">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
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
  
 <span data-ttu-id="4c9d3-155">다음 코드는 <xref:System.Data.OracleClient.OracleDataReader.Read> 의 및 메서드를 사용 하 여 이전 명령의 결과를 반환 합니다 <xref:System.Data.OracleClient.OracleDataReader.NextResult> <xref:System.Data.OracleClient.OracleDataReader> .</span><span class="sxs-lookup"><span data-stu-id="4c9d3-155">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="4c9d3-156">REF CURSOR 매개 변수가 순서대로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-156">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="4c9d3-157">다음 예에서는 이전 명령을 사용 하 여를 <xref:System.Data.DataSet> Oracle 패키지의 결과로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-157">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
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
> <span data-ttu-id="4c9d3-158">**OverflowException**을 방지 하려면에 값을 저장 하기 전에 Oracle 숫자 형식에서 유효한 .NET Framework 형식으로의 변환을 처리 하는 것이 좋습니다 <xref:System.Data.DataRow> .</span><span class="sxs-lookup"><span data-stu-id="4c9d3-158">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="4c9d3-159">이벤트를 사용 하 여 <xref:System.Data.Common.DataAdapter.FillError> **OverflowException** 발생 했는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-159">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="4c9d3-160">이벤트에 대 한 자세한 내용은 <xref:System.Data.Common.DataAdapter.FillError> [DataAdapter 이벤트 처리](handling-dataadapter-events.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c9d3-160">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c9d3-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c9d3-161">See also</span></span>

- [<span data-ttu-id="4c9d3-162">DataAdapters 및 DataReaders</span><span class="sxs-lookup"><span data-stu-id="4c9d3-162">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="4c9d3-163">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="4c9d3-163">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="4c9d3-164">데이터베이스 스키마 정보 검색</span><span class="sxs-lookup"><span data-stu-id="4c9d3-164">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="4c9d3-165">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="4c9d3-165">ADO.NET Overview</span></span>](ado-net-overview.md)
