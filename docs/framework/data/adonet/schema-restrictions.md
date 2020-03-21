---
title: 스키마 제한
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 17c42c5131252993d1f16e4a2f7a6450f0984d11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149013"
---
# <a name="schema-restrictions"></a>스키마 제한
**GetSchema** 메서드의 두 번째 선택적 매개 변수는 반환되는 스키마 정보의 양을 제한하는 데 사용되는 제한이며 문자열 배열로 **GetSchema** 메서드에 전달됩니다. 배열의 위치는 전달할 수 있는 값을 결정하며 이 위치는 제한 번호와 동일합니다.  
  
 예를 들어 다음 표에는 .NET Framework Data Provider for SQL Server를 사용하는 "Table" 스키마 컬렉션에서 지원되는 제한에 대한 설명이 나와 있습니다. SQL Server 스키마 컬렉션의 추가 제한은 이 항목의 맨 마지막에 나열되어 있습니다.  
  
|제한 이름|매개 변수 이름|제한 기본값|제한 번호|  
|----------------------|--------------------|-------------------------|------------------------|  
|카탈로그|@Catalog|TABLE_CATALOG|1|  
|소유자|@Owner|TABLE_SCHEMA|2|  
|테이블|@Name|TABLE_NAME|3|  
|TableType|@TableType|TABLE_TYPE|4|  
  
## <a name="specifying-restriction-values"></a>제한 값 지정  
 "Tables" 스키마 컬렉션의 제한 중 하나를 사용하려면 네 가지 요소로 된 문자열 배열을 만든 다음 제한 번호와 일치하는 요소에 값을 지정하면 됩니다. 예를 들어 **GetSchema** 메서드에서 반환되는 테이블을 "Sales" 스키마의 해당 테이블으로만 제한하려면 배열의 두 번째 요소를 "Sales"로 설정한 다음 **GetSchema** 메서드에 전달합니다.  
  
> [!NOTE]
> `SqlClient` 및 `OracleClient`의 제한 컬렉션에는 하나의 추가 `ParameterName` 열이 있습니다. 제한 기본 열은 이전 버전과 여전히 호환되지만 현재는 무시됩니다. 문자열 대체보다는 매개 변수가 있는 쿼리를 사용하여 제한 값을 지정할 때 SQL 삽입 공격 위험을 최소화해야 합니다.  
  
> [!NOTE]
> 배열의 요소 개수는 지정된 스키마 컬렉션에 대해 지원되는 제한 개수보다 작거나 같아야 합니다. 그렇지 않으면 <xref:System.ArgumentException>이 throw됩니다. 제한의 최대 개수보다 작을 수 있으며 제한이 없으면 null(무제한)로 간주합니다.  
  
 .NET Framework 관리 공급자를 쿼리하여 "제한"인 제한 스키마 컬렉션의 이름으로 **GetSchema** 메서드를 호출하여 지원되는 제한 목록을 확인할 수 있습니다. 그러면 컬렉션 이름, 제한 이름, 기본 제한 값 및 제한 번호 목록과 함께 <xref:System.Data.DataTable>이 반환됩니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 SQL Server <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> <xref:System.Data.SqlClient.SqlConnection> 클래스에 .NET Framework 데이터 공급자 메서드를 사용하여 **AdventureWorks** 샘플 데이터베이스에 포함된 모든 테이블에 대한 스키마 정보를 검색하고 "Sales" 스키마의 해당 테이블로만 반환되는 정보를 제한하는 방법을 보여 줍니다.  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
    string connectionString =
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
        Console.WriteLine("Press any key to continue.");  
        Console.ReadKey();  
    }  
  }  
  
  private static string GetConnectionString()  
  {  
     // To avoid storing the connection string in your code,  
     // you can retrieve it from a configuration file.  
     return "Data Source=(local);Database=AdventureWorks;" +  
        "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="sql-server-schema-restrictions"></a>SQL Server 스키마 제한  
 다음 표에는 SQL Server 스키마 컬렉션의 제한이 나열되어 있습니다.  
  
### <a name="users"></a>사용자  
  
|제한 이름|매개 변수 이름|제한 기본값|제한 번호|  
|----------------------|--------------------|-------------------------|------------------------|  
|User_Name|@Name|name|1|  
  
### <a name="databases"></a>데이터베이스  
  
|제한 이름|매개 변수 이름|제한 기본값|제한 번호|  
|----------------------|--------------------|-------------------------|------------------------|  
|속성|@Name|속성|1|  
  
### <a name="tables"></a>테이블  
  
|제한 이름|매개 변수 이름|제한 기본값|제한 번호|  
|----------------------|--------------------|-------------------------|------------------------|  
|카탈로그|@Catalog|TABLE_CATALOG|1|  
|소유자|@Owner|TABLE_SCHEMA|2|  
|테이블|@Name|TABLE_NAME|3|  
|TableType|@TableType|TABLE_TYPE|4|  
  
### <a name="columns"></a>열  
  
|제한 이름|매개 변수 이름|제한 기본값|제한 번호|  
|----------------------|--------------------|-------------------------|------------------------|  
|카탈로그|@Catalog|TABLE_CATALOG|1|  
|소유자|@Owner|TABLE_SCHEMA|2|  
|테이블|@Table|TABLE_NAME|3|  
|열|@Column|COLUMN_NAME|4|  
  
### <a name="structuredtypemembers"></a>StructuredTypeMembers  
  
|제한 이름|매개 변수 이름|제한 기본값|제한 번호|  
|----------------------|--------------------|-------------------------|------------------------|  
|카탈로그|@Catalog|TABLE_CATALOG|1|  
|소유자|@Owner|TABLE_SCHEMA|2|  
|테이블|@Table|TABLE_NAME|3|  
|열|@Column|COLUMN_NAME|4|  
  
### <a name="views"></a>뷰  
  
|제한 이름|매개 변수 이름|제한 기본값|제한 번호|  
|----------------------|--------------------|-------------------------|------------------------|  
|카탈로그|@Catalog|TABLE_CATALOG|1|  
|소유자|@Owner|TABLE_SCHEMA|2|  
|테이블|@Table|TABLE_NAME|3|  
  
### <a name="viewcolumns"></a>ViewColumns  
  
|제한 이름|매개 변수 이름|제한 기본값|제한 번호|  
|----------------------|--------------------|-------------------------|------------------------|  
|카탈로그|@Catalog|VIEW_CATALOG|1|  
|소유자|@Owner|VIEW_SCHEMA|2|  
|테이블|@Table|VIEW_NAME|3|  
|열|@Column|COLUMN_NAME|4|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|제한 이름|매개 변수 이름|제한 기본값|제한 번호|  
|----------------------|--------------------|-------------------------|------------------------|  
|카탈로그|@Catalog|SPECIFIC_CATALOG|1|  
|소유자|@Owner|SPECIFIC_SCHEMA|2|  
|속성|@Name|SPECIFIC_NAME|3|  
|매개 변수|@Parameter|PARAMETER_NAME|4|  
  
### <a name="procedures"></a>프로시저  
  
|제한 이름|매개 변수 이름|제한 기본값|제한 번호|  
|----------------------|--------------------|-------------------------|------------------------|  
|카탈로그|@Catalog|SPECIFIC_CATALOG|1|  
|소유자|@Owner|SPECIFIC_SCHEMA|2|  
|속성|@Name|SPECIFIC_NAME|3|  
|Type|@Type|ROUTINE_TYPE|4|  
  
### <a name="indexcolumns"></a>IndexColumns  
  
|제한 이름|매개 변수 이름|제한 기본값|제한 번호|  
|----------------------|--------------------|-------------------------|------------------------|  
|카탈로그|@Catalog|db_name()|1|  
|소유자|@Owner|user_name()|2|  
|테이블|@Table|o.name|3|  
|ConstraintName|@ConstraintName|x.name|4|  
|열|@Column|c.name|5|  
  
### <a name="indexes"></a>인덱스  
  
|제한 이름|매개 변수 이름|제한 기본값|제한 번호|  
|----------------------|--------------------|-------------------------|------------------------|  
|카탈로그|@Catalog|db_name()|1|  
|소유자|@Owner|user_name()|2|  
|테이블|@Table|o.name|3|  
  
### <a name="userdefinedtypes"></a>UserDefinedTypes  
  
|제한 이름|매개 변수 이름|제한 기본값|제한 번호|  
|----------------------|--------------------|-------------------------|------------------------|  
|assembly_name|@AssemblyName|assemblies.name|1|  
|udt_name|@UDTName|types.assembly_class|2|  
  
### <a name="foreignkeys"></a>ForeignKeys  
  
|제한 이름|매개 변수 이름|제한 기본값|제한 번호|  
|----------------------|--------------------|-------------------------|------------------------|  
|카탈로그|@Catalog|CONSTRAINT_CATALOG|1|  
|소유자|@Owner|CONSTRAINT_SCHEMA|2|  
|테이블|@Table|TABLE_NAME|3|  
|속성|@Name|CONSTRAINT_NAME|4|  
  
## <a name="sql-server-2008-schema-restrictions"></a>SQL Server 2008  
 다음 표에는 SQL Server 2008 스키마 컬렉션의 제한이 나열되어 있습니다. 이러한 제한은 .NET Framework 버전 3.5 SP1 및 SQL Server 2008 이상에서 유효하며 이전 버전의 .NET Framework 및 SQL Server에서는 지원되지 않습니다.  
  
### <a name="columnsetcolumns"></a>ColumnSetColumns  
  
|제한 이름|매개 변수 이름|제한 기본값|제한 번호|  
|----------------------|--------------------|-------------------------|------------------------|  
|카탈로그|@Catalog|TABLE_CATALOG|1|  
|소유자|@Owner|TABLE_SCHEMA|2|  
|테이블|@Table|TABLE_NAME|3|  
  
### <a name="allcolumns"></a>AllColumns  
  
|제한 이름|매개 변수 이름|제한 기본값|제한 번호|  
|----------------------|--------------------|-------------------------|------------------------|  
|카탈로그|@Catalog|TABLE_CATALOG|1|  
|소유자|@Owner|TABLE_SCHEMA|2|  
|테이블|@Table|TABLE_NAME|3|  
|열|@Column|COLUMN_NAME|4|  
  
## <a name="see-also"></a>참고 항목

- [ADO.NET 개요](ado-net-overview.md)
