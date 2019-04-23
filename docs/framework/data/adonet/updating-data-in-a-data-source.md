---
title: 데이터 원본에서 데이터 업데이트
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
ms.openlocfilehash: a12fa587d5df0ed95dd0f15ccfbe2ef886185b9e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207482"
---
# <a name="updating-data-in-a-data-source"></a><span data-ttu-id="87f47-102">데이터 원본에서 데이터 업데이트</span><span class="sxs-lookup"><span data-stu-id="87f47-102">Updating Data in a Data Source</span></span>
<span data-ttu-id="87f47-103">INSERT, UPDATE 또는 DELETE와 같이 데이터를 수정하는 SQL 문은 행을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87f47-103">SQL statements that modify data (such as INSERT, UPDATE, or DELETE) do not return rows.</span></span> <span data-ttu-id="87f47-104">마찬가지로 대부분의 저장 프로시저도 동작을 수행하기는 하지만 행을 반환하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87f47-104">Similarly, many stored procedures perform an action but do not return rows.</span></span> <span data-ttu-id="87f47-105">만들기는 행을 반환 하지 않는 명령을 실행 하는 **명령** 적절 한 SQL 명령 사용 하 여 개체 및 **연결**, 필요한를 포함 하 여 **매개 변수**합니다.</span><span class="sxs-lookup"><span data-stu-id="87f47-105">To execute commands that do not return rows, create a **Command** object with the appropriate SQL command and a **Connection**, including any required **Parameters**.</span></span> <span data-ttu-id="87f47-106">사용 하 여 명령을 실행 합니다 **ExecuteNonQuery** 메서드의 **명령** 개체.</span><span class="sxs-lookup"><span data-stu-id="87f47-106">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="87f47-107">합니다 **ExecuteNonQuery** 메서드는 문 또는 저장된 프로시저 실행 된 영향을 받는 행 수를 나타내는 정수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f47-107">The **ExecuteNonQuery** method returns an integer that represents the number of rows affected by the statement or stored procedure that was executed.</span></span> <span data-ttu-id="87f47-108">여러 문을 실행하는 경우 반환되는 값은 실행된 모든 문에 의해 영향을 받는 레코드의 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="87f47-108">If multiple statements are executed, the value returned is the sum of the records affected by all of the statements executed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87f47-109">예제</span><span class="sxs-lookup"><span data-stu-id="87f47-109">Example</span></span>  
 <span data-ttu-id="87f47-110">다음 코드 예제를 사용 하 여 데이터베이스에 레코드를 삽입 하기 위해 INSERT 문을 실행 **ExecuteNonQuery**합니다.</span><span class="sxs-lookup"><span data-stu-id="87f47-110">The following code example executes an INSERT statement to insert a record into a database using **ExecuteNonQuery**.</span></span>  
  
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
  
 <span data-ttu-id="87f47-111">다음 코드 예제에서는 샘플의 코드에 의해 생성 된 저장된 프로시저를 실행 [카탈로그 작업 수행](../../../../docs/framework/data/adonet/performing-catalog-operations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="87f47-111">The following code example executes the stored procedure created by the sample code in [Performing Catalog Operations](../../../../docs/framework/data/adonet/performing-catalog-operations.md).</span></span> <span data-ttu-id="87f47-112">저장된 프로시저에서 아무 행도 반환 하므로 **ExecuteNonQuery** 메서드는 사용 되지 않지만 저장된 프로시저에서 입력된 매개 변수를 수신 하 고 출력 매개 변수 및 반환 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f47-112">No rows are returned by the stored procedure, so the **ExecuteNonQuery** method is used, but the stored procedure does receive an input parameter and returns an output parameter and a return value.</span></span>  
  
 <span data-ttu-id="87f47-113">에 대 한는 <xref:System.Data.OleDb.OleDbCommand> 개체를 **ReturnValue** 매개 변수를 추가 해야 합니다 **매개 변수** 컬렉션 첫 번째.</span><span class="sxs-lookup"><span data-stu-id="87f47-113">For the <xref:System.Data.OleDb.OleDbCommand> object, the **ReturnValue** parameter must be added to the **Parameters** collection first.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="87f47-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="87f47-114">See also</span></span>

- [<span data-ttu-id="87f47-115">명령을 사용하여 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="87f47-115">Using Commands to Modify Data</span></span>](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)
- [<span data-ttu-id="87f47-116">DataAdapter로 데이터 원본 업데이트</span><span class="sxs-lookup"><span data-stu-id="87f47-116">Updating Data Sources with DataAdapters</span></span>](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="87f47-117">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="87f47-117">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="87f47-118">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="87f47-118">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
