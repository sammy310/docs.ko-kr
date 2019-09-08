---
title: 카탈로그 작업 수행
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: 0291b6684092ec15fc672c39c909caf7781194e3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783250"
---
# <a name="performing-catalog-operations"></a><span data-ttu-id="4792d-102">카탈로그 작업 수행</span><span class="sxs-lookup"><span data-stu-id="4792d-102">Performing Catalog Operations</span></span>
<span data-ttu-id="4792d-103">CREATE TABLE 또는 CREATE PROCEDURE 문과 같이 데이터베이스 또는 카탈로그를 수정 하는 명령을 실행 하려면 적절 한 SQL 문과 **연결** 개체를 사용 하 여 **명령** 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4792d-103">To execute a command to modify a database or catalog, such as the CREATE TABLE or CREATE PROCEDURE statement, create a **Command** object using the appropriate SQL statements and a **Connection** object.</span></span> <span data-ttu-id="4792d-104">**Command** 개체의 **ExecuteNonQuery** 메서드를 사용 하 여 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4792d-104">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="4792d-105">다음 코드 예제에서는 Microsoft SQL Server 데이터베이스에 저장 프로시저를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4792d-105">The following code example creates a stored procedure in a Microsoft SQL Server database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4792d-106">참고자료</span><span class="sxs-lookup"><span data-stu-id="4792d-106">See also</span></span>

- [<span data-ttu-id="4792d-107">명령을 사용하여 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="4792d-107">Using Commands to Modify Data</span></span>](using-commands-to-modify-data.md)
- [<span data-ttu-id="4792d-108">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="4792d-108">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="4792d-109">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="4792d-109">ADO.NET Overview</span></span>](ado-net-overview.md)
