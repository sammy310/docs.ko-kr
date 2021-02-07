---
description: '자세한 정보: 데이터 원본에서 데이터 업데이트'
title: 데이터 원본에서 데이터 업데이트
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
ms.openlocfilehash: a55d6a53f4607908fa279474419803eac3963909
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766571"
---
# <a name="updating-data-in-a-data-source"></a><span data-ttu-id="a83b7-103">데이터 원본에서 데이터 업데이트</span><span class="sxs-lookup"><span data-stu-id="a83b7-103">Updating Data in a Data Source</span></span>

<span data-ttu-id="a83b7-104">INSERT, UPDATE 또는 DELETE와 같이 데이터를 수정하는 SQL 문은 행을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a83b7-104">SQL statements that modify data (such as INSERT, UPDATE, or DELETE) do not return rows.</span></span> <span data-ttu-id="a83b7-105">마찬가지로 대부분의 저장 프로시저도 동작을 수행하기는 하지만 행을 반환하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a83b7-105">Similarly, many stored procedures perform an action but do not return rows.</span></span> <span data-ttu-id="a83b7-106">행을 반환하지 않는 명령을 실행하려면 필요한 **Parameters** 를 포함하여 적절한 SQL 명령 및 **Connection** 으로 **Command** 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a83b7-106">To execute commands that do not return rows, create a **Command** object with the appropriate SQL command and a **Connection**, including any required **Parameters**.</span></span> <span data-ttu-id="a83b7-107">**Command** 개체의 **ExecuteNonQuery** 메서드를 사용 하 여 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a83b7-107">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="a83b7-108">**ExecuteNonQuery** 메서드는 실행된 문 또는 저장 프로시저의 영향을 받는 행의 수를 나타내는 정수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a83b7-108">The **ExecuteNonQuery** method returns an integer that represents the number of rows affected by the statement or stored procedure that was executed.</span></span> <span data-ttu-id="a83b7-109">여러 문을 실행하는 경우 반환되는 값은 실행된 모든 문에 의해 영향을 받는 레코드의 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="a83b7-109">If multiple statements are executed, the value returned is the sum of the records affected by all of the statements executed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a83b7-110">예</span><span class="sxs-lookup"><span data-stu-id="a83b7-110">Example</span></span>  

 <span data-ttu-id="a83b7-111">다음 코드 예제에서는 **ExecuteNonQuery** 를 사용하여 레코드를 데이터베이스에 삽입하기 위한 INSERT 문을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a83b7-111">The following code example executes an INSERT statement to insert a record into a database using **ExecuteNonQuery**.</span></span>  
  
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
  
 <span data-ttu-id="a83b7-112">다음 코드 예제에서는 [카탈로그 작업 수행](performing-catalog-operations.md)에 있는 샘플 코드에서 만든 저장 프로시저를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a83b7-112">The following code example executes the stored procedure created by the sample code in [Performing Catalog Operations](performing-catalog-operations.md).</span></span> <span data-ttu-id="a83b7-113">저장 프로시저가 행을 반환하지 않으므로 **ExecuteNonQuery** 메서드가 사용되지만 저장 프로시저는 입력 매개 변수를 받고 출력 매개 변수와 반환 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a83b7-113">No rows are returned by the stored procedure, so the **ExecuteNonQuery** method is used, but the stored procedure does receive an input parameter and returns an output parameter and a return value.</span></span>  
  
 <span data-ttu-id="a83b7-114">개체의 경우 <xref:System.Data.OleDb.OleDbCommand> **ReturnValue** 매개 변수를 먼저 **Parameters** 컬렉션에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a83b7-114">For the <xref:System.Data.OleDb.OleDbCommand> object, the **ReturnValue** parameter must be added to the **Parameters** collection first.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a83b7-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a83b7-115">See also</span></span>

- [<span data-ttu-id="a83b7-116">명령을 사용 하 여 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="a83b7-116">Using Commands to Modify Data</span></span>](using-commands-to-modify-data.md)
- [<span data-ttu-id="a83b7-117">DataAdapters로 데이터 원본 업데이트</span><span class="sxs-lookup"><span data-stu-id="a83b7-117">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="a83b7-118">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="a83b7-118">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="a83b7-119">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="a83b7-119">ADO.NET Overview</span></span>](ado-net-overview.md)
