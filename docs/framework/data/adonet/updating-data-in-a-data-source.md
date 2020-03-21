---
title: 데이터 원본에서 데이터 업데이트
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
ms.openlocfilehash: 18bb03e17b19243ee1bc6e3f7ebd70afb4d4c60b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174448"
---
# <a name="updating-data-in-a-data-source"></a>데이터 원본에서 데이터 업데이트
INSERT, UPDATE 또는 DELETE와 같이 데이터를 수정하는 SQL 문은 행을 반환하지 않습니다. 마찬가지로 대부분의 저장 프로시저도 동작을 수행하기는 하지만 행을 반환하지는 않습니다. 행을 반환하지 않는 명령을 실행하려면 필요한 **매개 변수를**포함하여 적절한 SQL 명령과 **연결을**사용하여 **Command** 개체를 만듭니다. **Command** 개체의 **ExecuteNonQuery** 메서드를 사용 하 고 명령을 실행 합니다.  
  
 **ExecuteNonQuery** 메서드는 실행 된 명령문 또는 저장 프로시저의 영향을 받는 행 수를 나타내는 정수를 반환 합니다. 여러 문을 실행하는 경우 반환되는 값은 실행된 모든 문에 의해 영향을 받는 레코드의 합계입니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제는 INSERT 문을 실행하여 **ExecuteNonQuery**를 사용하여 데이터베이스에 레코드를 삽입합니다.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
connection.Open()  
  
Dim queryString As String = "INSERT INTO Customers " & _  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
Dim recordsAffected As Int32 = command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
string queryString = "INSERT INTO Customers " +  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
Int32 recordsAffected = command.ExecuteNonQuery();  
```  
  
 다음 코드 예제에서는 [카탈로그 작업 수행에서](performing-catalog-operations.md)샘플 코드에서 만든 저장 프로시저를 실행합니다. 저장 프로시저에서 행이 반환되지 않으므로 **ExecuteNonQuery** 메서드가 사용되지만 저장 프로시저는 입력 매개 변수를 수신하고 출력 매개 변수와 반환 값을 반환합니다.  
  
 개체의 <xref:System.Data.OleDb.OleDbCommand> 경우 **ReturnValue** 매개 변수를 **먼저 매개 변수** 컬렉션에 추가해야 합니다.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim command As SqlCommand = _  
   New SqlCommand("InsertCategory" , connection)  
command.CommandType = CommandType.StoredProcedure  
  
Dim parameter As SqlParameter = _  
 command.Parameters.Add("@RowCount", SqlDbType.Int)  
parameter.Direction = ParameterDirection.ReturnValue  
  
parameter = command.Parameters.Add( _  
  "@CategoryName", SqlDbType.NChar, 15)  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int)  
parameter.Direction = ParameterDirection.Output  
  
command.Parameters("@CategoryName").Value = "New Category"  
command.ExecuteNonQuery()  
  
Dim categoryID As Int32 = CInt(command.Parameters("@Identity").Value)  
Dim rowCount As Int32 = CInt(command.Parameters("@RowCount").Value)
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlCommand command = new SqlCommand("InsertCategory" , connection);  
command.CommandType = CommandType.StoredProcedure;  
  
SqlParameter parameter = command.Parameters.Add(  
  "@RowCount", SqlDbType.Int);  
parameter.Direction = ParameterDirection.ReturnValue;  
  
parameter = command.Parameters.Add(  
  "@CategoryName", SqlDbType.NChar, 15);  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int);  
parameter.Direction = ParameterDirection.Output;  
  
command.Parameters["@CategoryName"].Value = "New Category";  
command.ExecuteNonQuery();  
  
Int32 categoryID = (Int32) command.Parameters["@Identity"].Value;  
Int32 rowCount = (Int32) command.Parameters["@RowCount"].Value;  
```  
  
## <a name="see-also"></a>참고 항목

- [명령을 사용하여 데이터 수정](using-commands-to-modify-data.md)
- [DataAdapter로 데이터 원본 업데이트](updating-data-sources-with-dataadapters.md)
- [명령 및 매개 변수](commands-and-parameters.md)
- [ADO.NET 개요](ado-net-overview.md)
