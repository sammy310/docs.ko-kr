---
title: DataReader를 사용하여 데이터 검색
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 88cd85ce343aaab08b944f81c9659918014da0a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149026"
---
# <a name="retrieve-data-using-a-datareader"></a>데이터 리더를 사용하여 데이터 검색
**DataReader를**사용하여 데이터를 검색하려면 **Command** 개체의 인스턴스를 만든 다음 **Command.ExecuteReader를** 호출하여 **DataReader를** 만들어 데이터 원본에서 행을 검색합니다. **DataReader는** 절차 논리가 데이터 원본의 결과를 순차적으로 효율적으로 처리할 수 있도록 버퍼링되지 않은 데이터 스트림을 제공합니다. **DataReader는** 데이터가 메모리에 캐시되지 않기 때문에 많은 양의 데이터를 검색할 때 좋은 선택입니다.

다음 예제에서는 유효한 **DataReader를** `reader` 나타내고 `command` 유효한 Command 개체를 나타내는 DataReader를 사용하는 것을 보여 줍니다.  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

**DataReader.Read** 메서드를 사용하여 쿼리 결과에서 행을 가져옵니다. 반환된 행의 각 열에 액세스하여 열의 이름 또는 서수 번호를 **DataReader**에 전달할 수 있습니다. 그러나 최상의 성능을 위해 **DataReader는** 네이티브 데이터**형식(GetDateTime,** **GetDouble,** **GetGuid,** **GetInt32**등)에서 열 값에 액세스할 수 있는 일련의 메서드를 제공합니다. 데이터 공급자 별 **DataReaders에**대한 형식이 있는 접근자 <xref:System.Data.SqlClient.SqlDataReader>메서드 목록은 및 을 참조하십시오. <xref:System.Data.OleDb.OleDbDataReader> 기본 데이터 형식을 알고 있는 경우 형식이 지정된 접근자 메서드를 사용하면 열 값을 검색할 때 필요한 변환 의 양이 줄어듭니다.  
  
 다음 예제는 **DataReader** 개체를 통해 다시 발생 하 고 각 행에서 두 개의 열을 반환 합니다.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a>DataReader 닫기  
 DataReader 개체 사용을 완료하면 항상 **Close** 메서드를 **호출합니다.**  
  
 **Command에** 출력 매개 변수 또는 반환 값이 포함되어 있는 경우 **DataReader가** 닫혀야 해당 값을 사용할 수 없습니다.  
  
 **DataReader가** 열려 있는 동안 **연결은** 해당 **DataReader**에서만 사용됩니다. 원래 **DataReader가** 닫혀있을 때까지 다른 **DataReader를**만드는 것을 포함하여 **연결에**대한 명령을 실행할 수 없습니다.  
  
> [!NOTE]
> **연결,** **DataReader**또는 클래스의 **Finalize** 메서드에서 관리되는 다른 개체에서 **닫기** 또는 **삭제를** 호출하지 마십시오. 종료자에서는 클래스에 직접 속한 관리되지 않는 리소스만 해제합니다. 클래스에서 관리되지 않는 리소스를 소유하지 않는 경우 클래스 정의에 **Finalize** 메서드를 포함하지 마십시오. 자세한 내용은 [가비지 수집](../../../standard/garbage-collection/index.md)을 참조하십시오.  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>NextResult를 사용하여 여러 결과 집합 검색  
 **DataReader가** 여러 결과 집합을 반환하는 경우 **NextResult** 메서드를 호출하여 결과 집합을 순차적으로 반복합니다. 다음 예제에서는 <xref:System.Data.SqlClient.SqlDataReader>가 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 메서드를 사용하여 두 가지 SELECT 문 결과를 처리하는 방법을 보여 줍니다.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>데이터 리더에서 스키마 정보 얻기  
 **DataReader가** 열려 있는 동안 **GetSchemaTable** 메서드를 사용하여 현재 결과 집합에 대한 스키마 정보를 검색할 수 있습니다. **GetSchemaTable** 현재 <xref:System.Data.DataTable> 결과 집합에 대 한 스키마 정보를 포함 하는 행 및 열으로 채워진 개체를 반환 합니다. **DataTable에는** 결과 집합의 각 열에 대해 하나의 행이 포함되어 있습니다. 스키마 테이블의 각 열은 결과 집합의 행에서 반환되는 열의 속성에 매핑되며, 여기서 **ColumnName은** 속성의 이름이며 열값은 속성값입니다. 다음 예제는 **DataReader에**대한 스키마 정보를 기록합니다.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>OLE DB 챕터 작업  
 계층적 행 집합 또는 장(OLE DB 형식 **DBTYPE_HCHAPTER**ADO 형식 **adChapter)을**사용하여 검색할 수 <xref:System.Data.OleDb.OleDbDataReader>있습니다. 장을 포함하는 쿼리가 **DataReader로**반환되면 해당 **DataReader의** 열로 장이 반환되고 **DataReader** 개체로 노출됩니다.  
  
 ADO.NET **DataSet은** 테이블 간의 부모-자식 관계를 사용하여 계층적 행 집합을 나타내는 데도 사용할 수 있습니다. 자세한 내용은 [데이터 집합, 데이터 테이블 및 데이터 뷰를](./dataset-datatable-dataview/index.md)참조하십시오.  
  
 다음 코드 예제에서는 MSDataShape 공급자를 사용하여 고객 목록에 있는 각 고객의 주문에 대해 장 열을 생성합니다.  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a>오라클 REF 커솔러로 결과 반환  
 .NET Framework Data Provider for Oracle을 사용하면 Oracle REF CURSOR를 사용하여 쿼리 결과를 반환할 수 있습니다. Oracle REF CURSOR는 <xref:System.Data.OracleClient.OracleDataReader>로 반환됩니다.  
  
 메서드를 <xref:System.Data.OracleClient.OracleDataReader> 사용 하 여 Oracle REF CURSOR를 나타내는 개체를 검색할 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> 수 있습니다. 를 채우는 데 <xref:System.Data.OracleClient.OracleCommand> 사용되는 **SelectCommand로** 하나 이상의 Oracle REF CURSOR을 반환하는 <xref:System.Data.OracleClient.OracleDataAdapter> 것을 지정할 수도 <xref:System.Data.DataSet>있습니다.  
  
 Oracle 데이터 원본에서 반환된 REF CURSOR에 <xref:System.Data.OracleClient.OracleCommand> 액세스하려면 쿼리에 대한 을 만들고 REF CURSOR를 참조하는 출력 매개 변수를 을 의 컬렉션에 <xref:System.Data.OracleClient.OracleCommand.Parameters> 추가합니다. <xref:System.Data.OracleClient.OracleCommand> 매개 변수 이름은 쿼리의 REF CURSOR 매개 변수 이름과 일치해야 합니다. 매개 변수의 형식을 <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>으로 설정합니다. REF 커서에 대한 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> <xref:System.Data.OracleClient.OracleCommand> 반환 <xref:System.Data.OracleClient.OracleDataReader> 방법.  
  
 여러 <xref:System.Data.OracleClient.OracleCommand> REF 커서를 반환하는 경우 여러 출력 매개 변수를 추가합니다. 메서드를 호출하여 다른 REF CURSORs에 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> 액세스할 수 있습니다. 첫 번째 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> REF CURSOR를 <xref:System.Data.OracleClient.OracleDataReader> 참조하는 호출을 반환합니다. 그런 다음 메서드를 <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> 호출하여 후속 REF CURSORs에 액세스할 수 있습니다. <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> 컬렉션의 매개 변수는 REF CURSOR 출력 매개 변수와 <xref:System.Data.OracleClient.OracleDataReader> 이름으로 일치하지만 <xref:System.Data.OracleClient.OracleCommand.Parameters> 컬렉션에 추가된 순서대로 액세스합니다.  
  
 예를 들어, 다음과 같은 Oracle 패키지 및 패키지 본문이 있을 수 있습니다.  
  
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
  
 다음 코드는 <xref:System.Data.OracleClient.OracleCommand> 컬렉션에 형식의 <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> 두 매개 변수를 추가하여 이전 Oracle 패키지의 <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> REF CURSORs를 반환하는 코드를 만듭니다.  
  
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
  
 다음 코드는 의 메서드를 사용하여 <xref:System.Data.OracleClient.OracleDataReader.Read> <xref:System.Data.OracleClient.OracleDataReader.NextResult> 이전 명령의 <xref:System.Data.OracleClient.OracleDataReader>결과를 반환합니다. REF CURSOR 매개 변수가 순서대로 반환됩니다.  
  
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
  
 다음 예제에서는 이전 명령을 사용하여 <xref:System.Data.DataSet> Oracle 패키지의 결과로 a를 채웁니다.  
  
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
> **오버플로예외를**방지하려면 값을 에 저장하기 전에 Oracle NUMBER 형식에서 유효한 .NET Framework 유형으로의 변환도 처리하는 것이 <xref:System.Data.DataRow>좋습니다. <xref:System.Data.Common.DataAdapter.FillError> 이벤트를 사용하여 **오버플로예외가** 발생했는지 확인할 수 있습니다. <xref:System.Data.Common.DataAdapter.FillError> 이벤트에 대한 자세한 내용은 [데이터 어댑터 이벤트 처리를](handling-dataadapter-events.md)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- [DataAdapter 및 DataReader](dataadapters-and-datareaders.md)
- [명령 및 매개 변수](commands-and-parameters.md)
- [데이터베이스 스키마 정보 검색](retrieving-database-schema-information.md)
- [ADO.NET 개요](ado-net-overview.md)
