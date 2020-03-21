---
title: 카탈로그 작업 수행
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: bedeb4e9c510a3feeedc038e9c4cef6c4721e345
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149247"
---
# <a name="performing-catalog-operations"></a><span data-ttu-id="a8ef1-102">카탈로그 작업 수행</span><span class="sxs-lookup"><span data-stu-id="a8ef1-102">Performing Catalog Operations</span></span>
<span data-ttu-id="a8ef1-103">테이블 만들기 또는 프로시저 만들기 문과 같은 데이터베이스 또는 카탈로그를 수정하는 명령을 실행하려면 적절한 SQL 문과 **연결** 개체를 사용하여 **Command** 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8ef1-103">To execute a command to modify a database or catalog, such as the CREATE TABLE or CREATE PROCEDURE statement, create a **Command** object using the appropriate SQL statements and a **Connection** object.</span></span> <span data-ttu-id="a8ef1-104">**Command** 개체의 **ExecuteNonQuery** 메서드를 사용 하 고 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ef1-104">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="a8ef1-105">다음 코드 예제에서는 Microsoft SQL Server 데이터베이스에 저장 프로시저를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8ef1-105">The following code example creates a stored procedure in a Microsoft SQL Server database.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim queryString As String = "CREATE PROCEDURE InsertCategory " & _  
    "@CategoryName nchar(15), " & _  
    "@Identity int OUT " & _  
    "AS " & _  
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " & _  
    "SET @Identity = @@Identity " & _  
    "RETURN @@ROWCOUNT"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
string queryString = "CREATE PROCEDURE InsertCategory  " +
    "@CategoryName nchar(15), " +  
    "@Identity int OUT " +  
    "AS " +
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " +
    "SET @Identity = @@Identity " +  
    "RETURN @@ROWCOUNT";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
command.ExecuteNonQuery();  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8ef1-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8ef1-106">See also</span></span>

- [<span data-ttu-id="a8ef1-107">명령을 사용하여 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="a8ef1-107">Using Commands to Modify Data</span></span>](using-commands-to-modify-data.md)
- [<span data-ttu-id="a8ef1-108">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="a8ef1-108">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="a8ef1-109">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="a8ef1-109">ADO.NET Overview</span></span>](ado-net-overview.md)
