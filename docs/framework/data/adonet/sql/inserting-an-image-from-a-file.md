---
description: '자세히 알아보기: 파일에서 이미지 삽입'
title: 파일에서 이미지 삽입
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 35900aa2-5615-4174-8212-ba184c6b82fb
ms.openlocfilehash: 009b652988a6ce5dc532d3af926f865f7fc806e0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663198"
---
# <a name="inserting-an-image-from-a-file"></a>파일에서 이미지 삽입

데이터 원본에 있는 필드의 유형에 따라 BLOB(Binary Large Object) 이진 또는 문자 데이터로 데이터베이스에 쓸 수 있습니다. BLOB은 일반적으로 문서와 그림을 포함하는 `text`, `ntext` 및 `image` 데이터 형식을 지칭하는 일반 용어입니다.  
  
 데이터베이스에 BLOB 값을 쓰려면 적절 한 INSERT 또는 UPDATE 문을 실행 하 고 BLOB 값을 입력 매개 변수로 전달 합니다 ( [매개 변수 및 매개 변수 데이터 형식 구성](../configuring-parameters-and-parameter-data-types.md)참조). BLOB이 텍스트로 저장된 경우(예: SQL Server `text` 필드) BLOB을 문자열 매개 변수로 전달할 수 있습니다. BLOB이 이진 형식으로 저장된 경우(예: SQL Server `image` 필드) `byte` 형식의 배열을 이진 매개 변수로 전달할 수 있습니다.  
  
## <a name="example"></a>예제  

 다음 코드 예제에서는 Northwind 데이터베이스의 Employees 테이블에 직원 정보를 추가합니다. 직원의 사진을 파일에서 읽고 테이블의 Photo 필드(이미지 필드)에 추가합니다.  
  
```vb  
Public Shared Sub AddEmployee( _  
  lastName As String, _  
  firstName As String, _  
  title As String, _  
  hireDate As DateTime, _  
  reportsTo As Integer, _  
  photoFilePath As String, _  
  connectionString As String)  
  
  Dim photo() as Byte = GetPhoto(photoFilePath)  
  
  Using connection As SqlConnection = New SqlConnection( _  
    connectionString)  
  
  Dim command As SqlCommand = New SqlCommand( _  
    "INSERT INTO Employees (LastName, FirstName, Title, " & _  
    "HireDate, ReportsTo, Photo) " & _  
    "Values(@LastName, @FirstName, @Title, " & _  
    "@HireDate, @ReportsTo, @Photo)", connection)
  
  command.Parameters.Add("@LastName",  _  
    SqlDbType.NVarChar, 20).Value = lastName  
  command.Parameters.Add("@FirstName", _  
    SqlDbType.NVarChar, 10).Value = firstName  
  command.Parameters.Add("@Title", _  
    SqlDbType.NVarChar, 30).Value = title  
  command.Parameters.Add("@HireDate", _  
    SqlDbType.DateTime).Value = hireDate  
  command.Parameters.Add("@ReportsTo", _  
    SqlDbType.Int).Value = reportsTo  
  
  command.Parameters.Add("@Photo", _  
    SqlDbType.Image, photo.Length).Value = photo  
  
  connection.Open()  
  command.ExecuteNonQuery()  
  
  End Using  
End Sub  
  
Public Shared Function GetPhoto(filePath As String) As Byte()  
  Dim stream As FileStream = new FileStream( _  
     filePath, FileMode.Open, FileAccess.Read)  
  Dim reader As BinaryReader = new BinaryReader(stream)  
  
  Dim photo() As Byte = reader.ReadBytes(stream.Length)  
  
  reader.Close()  
  stream.Close()  
  
  Return photo  
End Function  
```  
  
```csharp  
public static void AddEmployee(  
  string lastName,
  string firstName,
  string title,
  DateTime hireDate,
  int reportsTo,
  string photoFilePath,
  string connectionString)  
{  
  byte[] photo = GetPhoto(photoFilePath);  
  
  using (SqlConnection connection = new SqlConnection(  
    connectionString))  
  
  SqlCommand command = new SqlCommand(  
    "INSERT INTO Employees (LastName, FirstName, " +  
    "Title, HireDate, ReportsTo, Photo) " +  
    "Values(@LastName, @FirstName, @Title, " +  
    "@HireDate, @ReportsTo, @Photo)", connection);
  
  command.Parameters.Add("@LastName",
     SqlDbType.NVarChar, 20).Value = lastName;  
  command.Parameters.Add("@FirstName",
      SqlDbType.NVarChar, 10).Value = firstName;  
  command.Parameters.Add("@Title",
      SqlDbType.NVarChar, 30).Value = title;  
  command.Parameters.Add("@HireDate",
       SqlDbType.DateTime).Value = hireDate;  
  command.Parameters.Add("@ReportsTo",
      SqlDbType.Int).Value = reportsTo;  
  
  command.Parameters.Add("@Photo",  
      SqlDbType.Image, photo.Length).Value = photo;  
  
  connection.Open();  
  command.ExecuteNonQuery();  
  }  
}  
  
public static byte[] GetPhoto(string filePath)  
{  
  FileStream stream = new FileStream(  
      filePath, FileMode.Open, FileAccess.Read);  
  BinaryReader reader = new BinaryReader(stream);  
  
  byte[] photo = reader.ReadBytes((int)stream.Length);  
  
  reader.Close();  
  stream.Close();  
  
  return photo;  
}  
```  
  
## <a name="see-also"></a>참고 항목

- [명령을 사용 하 여 데이터 수정](../using-commands-to-modify-data.md)
- [이진 데이터 검색](../retrieving-binary-data.md)
- [SQL Server 이진 및 큰 값 데이터](sql-server-binary-and-large-value-data.md)
- [SQL Server 데이터 형식 매핑](../sql-server-data-type-mappings.md)
- [ADO.NET 개요](../ado-net-overview.md)
