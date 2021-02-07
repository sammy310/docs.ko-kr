---
description: '자세한 정보: 카탈로그 작업 수행'
title: 카탈로그 작업 수행
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: c484e3a56d846de66c6e13b374efe58430ab86b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754344"
---
# <a name="performing-catalog-operations"></a>카탈로그 작업 수행

데이터베이스 또는 카탈로그를 수정하는 CREATE TABLE 또는 CREATE PROCEDURE 문과 같은 명령을 실행하려면 적절한 SQL 문과 **Connection** 개체를 사용하여 **Command** 개체를 만듭니다. **Command** 개체의 **ExecuteNonQuery** 메서드를 사용 하 여 명령을 실행 합니다.  
  
 다음 코드 예제에서는 Microsoft SQL Server 데이터베이스에 저장 프로시저를 만듭니다.  
  
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
  
## <a name="see-also"></a>참조

- [명령을 사용 하 여 데이터 수정](using-commands-to-modify-data.md)
- [명령 및 매개 변수](commands-and-parameters.md)
- [ADO.NET 개요](ado-net-overview.md)
