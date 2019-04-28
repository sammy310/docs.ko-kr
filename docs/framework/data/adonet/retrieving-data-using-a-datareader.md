---
title: DataReader를 사용하여 데이터 검색
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 8063f239123ec1a2f2650adf9d76f7ceaaa50673
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61664262"
---
# <a name="retrieve-data-using-a-datareader"></a>DataReader를 사용 하 여 데이터를 검색 합니다.
사용 하 여 데이터를 검색 하는 **DataReader**의 인스턴스를 만듭니다 합니다 **명령** 개체를 만든 다음을 **DataReader** 호출 하 여 **Command.ExecuteReader**  데이터 원본에서 행을 검색 합니다. 합니다 **DataReader** 절차적 논리 없이 효율적으로 데이터 소스에서 결과 순차적으로 처리할 수 있도록 데이터를 버퍼링 되지 않은 스트림을 제공 합니다. 합니다 **DataReader** 데이터가 메모리에 캐시 되지 않기 때문에 많은 양의 데이터를 검색 하는 경우 적합 합니다.

다음 예제를 사용 하는 **DataReader**여기서 `reader` 올바른 DataReader를 나타내는 및 `command` 올바른 Command 개체를 나타냅니다.  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

사용 된 **DataReader.Read** 메서드는 쿼리 결과에서 행을 가져오려고 합니다. 이름 또는 열의 서 수 번호를 전달 하 여 반환된 된 행의 각 열에 액세스할 수 있습니다 합니다 **DataReader**합니다. 최상의 성능을 위해 합니다 **DataReader** 일련의 네이티브 데이터 형식으로 열 값에 액세스할 수 있도록 하는 메서드를 제공 (**GetDateTime**, **GetDouble**하십시오 **GetGuid**를 **GetInt32**등). 데이터 공급자별으로 형식화 된 접근자 메서드 목록을 **DataReaders**를 참조 하십시오 <xref:System.Data.OleDb.OleDbDataReader> 및 <xref:System.Data.SqlClient.SqlDataReader>합니다. 기본 데이터를 알고 있는 경우에 형식화 된 접근자 메서드를 사용 하 여 형식 열 값을 검색할 때 필요한 형식 변환의 크기를 줄입니다.  
  
 다음 예제에서는 반복을 **DataReader** 개체 및 각 행에서 두 개의 열을 반환 합니다.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a>DataReader 닫기  
 항상 호출 합니다 **닫기** 메서드를 사용 하 여 완료 한 후 합니다 **DataReader** 개체입니다.  
  
 경우에 **명령** 출력이 포함 값까지 사용할 수 없는 매개 변수 또는 반환 값을 **DataReader** 닫혀 합니다.  
  
 하는 동안를 **DataReader** 열려 있는 경우 합니다 **연결** 에서 단독으로 사용 중인 **DataReader**합니다. 에 대해 어떤 명령도 실행할 수 없습니다는 **연결**, 등 다른 **DataReader**, 원래 될 때까지 **DataReader** 닫혀 있습니다.  
  
> [!NOTE]
>  호출 하지 마세요 **닫기** 또는 **Dispose** 에 **연결**, **DataReader**, 또는 다른 관리 개체에는 **Finalize**  클래스의 메서드. 종료자에서는 클래스에 직접 속한 관리되지 않는 리소스만 해제합니다. 클래스는 관리 되지 않는 리소스를 소유 하지 않습니다, 경우 포함 되지 않습니다는 **Finalize** 클래스 정의에 메서드. 자세한 내용은 [가비지 수집](../../../../docs/standard/garbage-collection/index.md)합니다.  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>NextResult를 사용 하 여 집합 여러 결과 검색 합니다.  
 경우는 **DataReader** 호출 여러 결과 집합을 반환 합니다 **NextResult** 결과 반복 하는 메서드를 순차적으로 설정 합니다. 다음 예제에서는 <xref:System.Data.SqlClient.SqlDataReader>가 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 메서드를 사용하여 두 가지 SELECT 문 결과를 처리하는 방법을 보여 줍니다.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>DataReader에서 스키마 정보 가져오기  
 하는 동안를 **DataReader** 가 열기를 가져오면 현재 결과 사용 하 여 집합에 대 한 스키마 정보를 **GetSchemaTable** 메서드. **GetSchemaTable** 반환을 <xref:System.Data.DataTable> 현재 결과 집합에 대 한 스키마 정보를 포함 하는 행과 열으로 채워진 개체입니다. 합니다 **DataTable** 결과 집합의 각 열에 대해 하나의 행을 포함 합니다. 스키마 테이블의 각 열에 반환 된 열의 속성에 매핑됩니다 있는 결과의 행을 설정 합니다 **ColumnName** 속성의 이름이 며 열의 값은 속성의 값입니다. 다음 예제에 대 한 스키마 정보를 씁니다 **DataReader**합니다.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>OLE DB 장 사용  
 계층적 행 집합 또는 장 (OLE DB 형식 **DBTYPE_HCHAPTER**, ADO 형식 **adChapter**)를 사용 하 여 검색할 수는 <xref:System.Data.OleDb.OleDbDataReader>합니다. 장을 포함 하는 쿼리로 반환 될 때를 **DataReader**의 열으로 반환 되는 **DataReader** 으로 노출 되는 **DataReader** 개체.  
  
 ADO.NET **데이터 집합** 테이블 간의 부모-자식 관계를 사용 하 여 계층적 행 집합을 나타내는 데 사용할 수도 있습니다. 자세한 내용은 [Dataset, Datatable 및 Dataview](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)합니다.  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Oracle REF Cursor를 사용 하 여 결과 반환합니다.  
 .NET Framework Data Provider for Oracle을 사용하면 Oracle REF CURSOR를 사용하여 쿼리 결과를 반환할 수 있습니다. Oracle REF CURSOR는 <xref:System.Data.OracleClient.OracleDataReader>로 반환됩니다.  
  
 검색할 수 있습니다는 <xref:System.Data.OracleClient.OracleDataReader> 를 사용 하 여 Oracle REF CURSOR를 나타내는 개체를 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> 메서드. 지정할 수도 있습니다는 <xref:System.Data.OracleClient.OracleCommand> 으로 하나 이상의 Oracle REF Cursor를 반환 하는 합니다 **SelectCommand** 에 대 한는 <xref:System.Data.OracleClient.OracleDataAdapter> 채우는 데는 <xref:System.Data.DataSet>.  
  
 Oracle 데이터 원본에서 반환 하는 REF CURSOR에 액세스 하려면 만듭니다는 <xref:System.Data.OracleClient.OracleCommand> 쿼리에 대 한 REF CURSOR를 참조 하는 출력 매개 변수를 추가 합니다 <xref:System.Data.OracleClient.OracleCommand.Parameters> 의 컬렉션에 <xref:System.Data.OracleClient.OracleCommand>합니다. 매개 변수 이름은 쿼리의 REF CURSOR 매개 변수 이름과 일치해야 합니다. 매개 변수의 형식을 설정 <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>합니다. <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> 메서드의 하 <xref:System.Data.OracleClient.OracleCommand> 반환는 <xref:System.Data.OracleClient.OracleDataReader> REF CURSOR에 대 한 합니다.  
  
 경우에 <xref:System.Data.OracleClient.OracleCommand> 여러 REF CURSOR를 반환 합니다. 여러 출력 매개 변수를 추가 합니다. 호출 하 여 서로 다른 REF Cursor에 액세스할 수 있습니다는 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> 메서드. 에 대 한 호출 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> 반환을 <xref:System.Data.OracleClient.OracleDataReader> 하면 첫 REF CURSOR를 참조 합니다. 호출할 수 있습니다는 <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> REF Cursor에 액세스 하는 방법입니다. 하지만 매개 변수 프로그램 <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> 이름별로 컬렉션 일치 REF CURSOR 출력 매개 변수를 <xref:System.Data.OracleClient.OracleDataReader> 에 추가 된 순서 대로 액세스는 <xref:System.Data.OracleClient.OracleCommand.Parameters> 컬렉션.  
  
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
  
 다음 코드는 <xref:System.Data.OracleClient.OracleCommand> 형식의 두 매개 변수를 추가 하 여 이전 Oracle 패키지에서 REF Cursor를 반환 하는 <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> 에 <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> 컬렉션입니다.  
  
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
  
 다음 코드를 사용 하 여 이전 명령 결과 반환 합니다 <xref:System.Data.OracleClient.OracleDataReader.Read> 및 <xref:System.Data.OracleClient.OracleDataReader.NextResult> 의 메서드는 <xref:System.Data.OracleClient.OracleDataReader>합니다. REF CURSOR 매개 변수가 순서대로 반환됩니다.  
  
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
  
 다음 예제에서는 명령을 사용 하 여 이전 채우기는 <xref:System.Data.DataSet> Oracle 패키지의 결과입니다.  
  
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
>  않으려면를 **OverflowException**, 모든 변환할 Oracle NUMBER 형식 유효한.NET Framework 형식으로 값을 저장 하기 전에 처리 하는 것이 좋습니다는 <xref:System.Data.DataRow>합니다. 사용할 수는 <xref:System.Data.Common.DataAdapter.FillError> 여부를 확인 하는 이벤트를 **OverflowException** 발생 했습니다. 에 대 한 자세한 합니다 <xref:System.Data.Common.DataAdapter.FillError> 이벤트를 참조 하세요 [DataAdapter 이벤트 처리](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [DataAdapter 및 DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [명령 및 매개 변수](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [데이터베이스 스키마 정보 검색](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
