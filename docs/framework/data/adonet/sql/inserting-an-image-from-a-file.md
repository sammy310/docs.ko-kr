---
title: 파일에서 이미지 삽입
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 35900aa2-5615-4174-8212-ba184c6b82fb
ms.openlocfilehash: e70576637d44e874532aa06da4fe94115ac8ed9c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194585"
---
# <a name="inserting-an-image-from-a-file"></a><span data-ttu-id="c42b0-102">파일에서 이미지 삽입</span><span class="sxs-lookup"><span data-stu-id="c42b0-102">Inserting an Image from a File</span></span>

<span data-ttu-id="c42b0-103">데이터 원본에 있는 필드의 유형에 따라 BLOB(Binary Large Object) 이진 또는 문자 데이터로 데이터베이스에 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c42b0-103">You can write a binary large object (BLOB) to a database as either binary or character data, depending on the type of field at your data source.</span></span> <span data-ttu-id="c42b0-104">BLOB은 일반적으로 문서와 그림을 포함하는 `text`, `ntext` 및 `image` 데이터 형식을 지칭하는 일반 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="c42b0-104">BLOB is a generic term that refers to the `text`, `ntext`, and `image` data types, which typically contain documents and pictures.</span></span>  
  
 <span data-ttu-id="c42b0-105">데이터베이스에 BLOB 값을 쓰려면 적절 한 INSERT 또는 UPDATE 문을 실행 하 고 BLOB 값을 입력 매개 변수로 전달 합니다 ( [매개 변수 및 매개 변수 데이터 형식 구성](../configuring-parameters-and-parameter-data-types.md)참조).</span><span class="sxs-lookup"><span data-stu-id="c42b0-105">To write a BLOB value to your database, issue the appropriate INSERT or UPDATE statement and pass the BLOB value as an input parameter (see [Configuring Parameters and Parameter Data Types](../configuring-parameters-and-parameter-data-types.md)).</span></span> <span data-ttu-id="c42b0-106">BLOB이 텍스트로 저장된 경우(예: SQL Server `text` 필드) BLOB을 문자열 매개 변수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c42b0-106">If your BLOB is stored as text, such as a SQL Server `text` field, you can pass the BLOB as a string parameter.</span></span> <span data-ttu-id="c42b0-107">BLOB이 이진 형식으로 저장된 경우(예: SQL Server `image` 필드) `byte` 형식의 배열을 이진 매개 변수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c42b0-107">If the BLOB is stored in binary format, such as a SQL Server `image` field, you can pass an array of type `byte` as a binary parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c42b0-108">예제</span><span class="sxs-lookup"><span data-stu-id="c42b0-108">Example</span></span>  

 <span data-ttu-id="c42b0-109">다음 코드 예제에서는 Northwind 데이터베이스의 Employees 테이블에 직원 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c42b0-109">The following code example adds employee information to the Employees table in the Northwind database.</span></span> <span data-ttu-id="c42b0-110">직원의 사진을 파일에서 읽고 테이블의 Photo 필드(이미지 필드)에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c42b0-110">A photo of the employee is read from a file and added to the Photo field in the table, which is an image field.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c42b0-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c42b0-111">See also</span></span>

- [<span data-ttu-id="c42b0-112">명령을 사용하여 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="c42b0-112">Using Commands to Modify Data</span></span>](../using-commands-to-modify-data.md)
- [<span data-ttu-id="c42b0-113">이진 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="c42b0-113">Retrieving Binary Data</span></span>](../retrieving-binary-data.md)
- [<span data-ttu-id="c42b0-114">이진 및 대량 값 데이터 SQL Server</span><span class="sxs-lookup"><span data-stu-id="c42b0-114">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="c42b0-115">SQL Server 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="c42b0-115">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="c42b0-116">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="c42b0-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
