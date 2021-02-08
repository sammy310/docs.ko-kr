---
description: '자세한 정보: FILESTREAM 데이터'
title: FILESTREAM 데이터
ms.date: 03/30/2017
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
ms.openlocfilehash: 0110be6b867a07ec1cd204e2a3de371367bbfa36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802049"
---
# <a name="filestream-data"></a><span data-ttu-id="f8736-103">FILESTREAM 데이터</span><span class="sxs-lookup"><span data-stu-id="f8736-103">FILESTREAM Data</span></span>

<span data-ttu-id="f8736-104">FILESTREAM 저장소 특성은 varbinary(max) 열에 저장된 이진(BLOB) 데이터를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-104">The FILESTREAM storage attribute is for binary (BLOB) data stored in a varbinary(max) column.</span></span> <span data-ttu-id="f8736-105">FILESTREAM 이전에는 이진 데이터를 저장하는 데 특별한 처리가 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-105">Before FILESTREAM, storing binary data required special handling.</span></span> <span data-ttu-id="f8736-106">텍스트 문서, 이미지 및 비디오와 같은 구조화되지 않은 데이터는 종종 데이터베이스 외부에 저장되므로 관리가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-106">Unstructured data, such as text documents, images and video, is often stored outside of the database, making it difficult to manage.</span></span>

> [!NOTE]
> <span data-ttu-id="f8736-107">SqlClient에서 FILESTREAM 데이터로 작업하려면 .NET Framework 3.5 SP1 이상을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-107">You must install the .NET Framework 3.5 SP1 (or later) to work with FILESTREAM data using SqlClient.</span></span>

<span data-ttu-id="f8736-108">varbinary(max) 열에 FILESTREAM 특성을 지정하면 SQL Server에서는 데이터베이스 파일 대신 로컬 NTFS 파일 시스템에 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-108">Specifying the FILESTREAM attribute on a varbinary(max) column causes SQL Server to store the data on the local NTFS file system instead of in the database file.</span></span> <span data-ttu-id="f8736-109">별도로 데이터가 저장되지만 데이터베이스에 저장된 varbinary(max) 데이터로 작업할 때와 동일한 Transact-SQL 문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-109">Although it is stored separately, you can use the same Transact-SQL statements that are supported for working with varbinary(max) data that is stored in the database.</span></span>

## <a name="sqlclient-support-for-filestream"></a><span data-ttu-id="f8736-110">FILESTREAM에 대한 SqlClient 지원</span><span class="sxs-lookup"><span data-stu-id="f8736-110">SqlClient Support for FILESTREAM</span></span>

<span data-ttu-id="f8736-111">SQL Server에 대 한 .NET Framework Data Provider는 <xref:System.Data.SqlClient> <xref:System.Data.SqlTypes.SqlFileStream> 네임 스페이스에 정의 된 클래스를 사용 하 여 FILESTREAM 데이터에 대 한 읽기 및 쓰기를 지원 합니다 <xref:System.Data.SqlTypes> .</span><span class="sxs-lookup"><span data-stu-id="f8736-111">The .NET Framework Data Provider for SQL Server, <xref:System.Data.SqlClient>, supports reading and writing to FILESTREAM data using the <xref:System.Data.SqlTypes.SqlFileStream> class defined in the <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="f8736-112">`SqlFileStream`은 데이터 스트림에 대한 읽기 및 쓰기 메서드를 제공하는 <xref:System.IO.Stream> 클래스에서 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-112">`SqlFileStream` inherits from the <xref:System.IO.Stream> class, which provides methods for reading and writing to streams of data.</span></span> <span data-ttu-id="f8736-113">스트림에서 읽으면 스트림의 데이터를 바이트 배열과 같은 데이터 구조로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-113">Reading from a stream transfers data from the stream into a data structure, such as an array of bytes.</span></span> <span data-ttu-id="f8736-114">쓰기는 데이터 구조에서 스트림으로 데이터를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-114">Writing transfers the data from the data structure into a stream.</span></span>

### <a name="creating-the-sql-server-table"></a><span data-ttu-id="f8736-115">SQL Server 테이블 만들기</span><span class="sxs-lookup"><span data-stu-id="f8736-115">Creating the SQL Server Table</span></span>

<span data-ttu-id="f8736-116">다음 Transact-SQL 문은 employees라는 테이블을 만들어 데이터 행을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-116">The following Transact-SQL statements creates a table named employees and inserts a row of data.</span></span> <span data-ttu-id="f8736-117">FILESTREAM 스토리지를 사용하도록 설정한 후에는 다음 코드 예제에 이 테이블을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-117">Once you have enabled FILESTREAM storage, you can use this table in conjunction with the code examples that follow.</span></span> <span data-ttu-id="f8736-118">SQL Server 온라인 설명서의 리소스 링크는 이 항목의 맨 마지막에 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-118">The links to resources in SQL Server Books Online are located at the end of this topic.</span></span>

```sql
CREATE TABLE employees
(
  EmployeeId INT  NOT NULL  PRIMARY KEY,
  Photo VARBINARY(MAX) FILESTREAM  NULL,
  RowGuid UNIQUEIDENTIFIER  NOT NULL  ROWGUIDCOL
  UNIQUE DEFAULT NEWID()
)
GO
Insert into employees
Values(1, 0x00, default)
GO
```

### <a name="example-reading-overwriting-and-inserting-filestream-data"></a><span data-ttu-id="f8736-119">예제: FILESTREAM 데이터 읽기, 덮어쓰기 및 삽입</span><span class="sxs-lookup"><span data-stu-id="f8736-119">Example: Reading, Overwriting, and Inserting FILESTREAM Data</span></span>

<span data-ttu-id="f8736-120">다음 샘플에서는 FILESTREAM에서 데이터를 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-120">The following sample demonstrates how to read data from a FILESTREAM.</span></span> <span data-ttu-id="f8736-121">이 코드는 파일에 대한 논리적 경로를 가져와 `FileAccess`를 `Read`로 설정하고 `FileOptions`를 `SequentialScan`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-121">The code gets the logical path to the file, setting the `FileAccess` to `Read` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="f8736-122">그런 다음 코드는 바이트를 SqlFileStream에서 버퍼로 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-122">The code then reads the bytes from the SqlFileStream into the buffer.</span></span> <span data-ttu-id="f8736-123">그러면 바이트가 콘솔 창에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-123">The bytes are then written to the console window.</span></span>

<span data-ttu-id="f8736-124">또한 이 샘플에서는 모든 기존 데이터를 덮어쓰도록 FILESTREAM에 데이터를 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-124">The sample also demonstrates how to write data to a FILESTREAM in which all existing data is overwritten.</span></span> <span data-ttu-id="f8736-125">이 코드는 파일에 대한 논리적 경로를 가져오고 `SqlFileStream`을 만들어 `FileAccess`를 `Write`로 설정하고 `FileOptions`를 `SequentialScan`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-125">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `Write` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="f8736-126">단일 바이트를 `SqlFileStream`에 기록하여 파일의 모든 데이터를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-126">A single byte is written to the `SqlFileStream`, replacing any data in the file.</span></span>

<span data-ttu-id="f8736-127">예제에서는 Seek 메서드를 사용하여 파일 끝에 데이터를 추가하는 방법으로 FILESTREAM에 데이터를 쓰는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-127">The sample also demonstrates how to write data to a FILESTREAM by using the Seek method to append data to the end of the file.</span></span> <span data-ttu-id="f8736-128">이 코드는 파일에 대한 논리적 경로를 가져오고 `SqlFileStream`을 만들어 `FileAccess`를 `ReadWrite`로 설정하고 `FileOptions`를 `SequentialScan`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-128">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `ReadWrite` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="f8736-129">이 코드는 Seek 메서드를 사용하여 파일의 끝을 검색하고, 기존 파일에 단일 바이트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-129">The code uses the Seek method to seek to the end of the file, appending a single byte to the existing file.</span></span>

```csharp
using System;
using System.Data.SqlClient;
using System.Data.SqlTypes;
using System.Data;
using System.IO;

namespace FileStreamTest
{
    class Program
    {
        static void Main(string[] args)
        {
            SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder("server=(local);integrated security=true;database=myDB");
            ReadFileStream(builder);
            OverwriteFileStream(builder);
            InsertFileStream(builder);

            Console.WriteLine("Done");
        }

        private static void ReadFileStream(SqlConnectionStringBuilder connStringBuilder)
        {
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))
            {
                connection.Open();
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);

                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);
                command.Transaction = tran;

                using (SqlDataReader reader = command.ExecuteReader())
                {
                    while (reader.Read())
                    {
                        // Get the pointer for the file
                        string path = reader.GetString(0);
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;

                        // Create the SqlFileStream
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Read, FileOptions.SequentialScan, allocationSize: 0))
                        {
                            // Read the contents as bytes and write them to the console
                            for (long index = 0; index < fileStream.Length; index++)
                            {
                                Console.WriteLine(fileStream.ReadByte());
                            }
                        }
                    }
                }
                tran.Commit();
            }
        }

        private static void OverwriteFileStream(SqlConnectionStringBuilder connStringBuilder)
        {
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))
            {
                connection.Open();

                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);

                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);
                command.Transaction = tran;

                using (SqlDataReader reader = command.ExecuteReader())
                {
                    while (reader.Read())
                    {
                        // Get the pointer for file
                        string path = reader.GetString(0);
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;

                        // Create the SqlFileStream
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))
                        {
                            // Write a single byte to the file. This will
                            // replace any data in the file.
                            fileStream.WriteByte(0x01);
                        }
                    }
                }
                tran.Commit();
            }
        }

        private static void InsertFileStream(SqlConnectionStringBuilder connStringBuilder)
        {
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))
            {
                connection.Open();

                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);

                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);
                command.Transaction = tran;

                using (SqlDataReader reader = command.ExecuteReader())
                {
                    while (reader.Read())
                    {
                        // Get the pointer for file
                        string path = reader.GetString(0);
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;

                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.ReadWrite, FileOptions.SequentialScan, allocationSize: 0))
                        {
                            // Seek to the end of the file
                            fileStream.Seek(0, SeekOrigin.End);

                            // Append a single byte
                            fileStream.WriteByte(0x01);
                        }
                    }
                }
                tran.Commit();
            }

        }
    }
}
```

<span data-ttu-id="f8736-130">다른 샘플은 [파일 스트림 열에 이진 데이터를 저장 및 페치하는 방법](https://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8736-130">For another sample, see [How to store and fetch binary data into a file stream column](https://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span></span>

## <a name="resources-in-sql-server-books-online"></a><span data-ttu-id="f8736-131">SQL Server 온라인 설명서 내 리소스</span><span class="sxs-lookup"><span data-stu-id="f8736-131">Resources in SQL Server Books Online</span></span>

<span data-ttu-id="f8736-132">FILESTREAM에 대한 자세한 설명은 SQL Server 온라인 설명서의 다음 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-132">The complete documentation for FILESTREAM is located in the following sections in SQL Server Books Online.</span></span>

|<span data-ttu-id="f8736-133">항목</span><span class="sxs-lookup"><span data-stu-id="f8736-133">Topic</span></span>|<span data-ttu-id="f8736-134">Description</span><span class="sxs-lookup"><span data-stu-id="f8736-134">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="f8736-135">[FILESTREAM [SQL Server]](/sql/relational-databases/blob/filestream-sql-server)</span><span class="sxs-lookup"><span data-stu-id="f8736-135">[FILESTREAM (SQL Server)](/sql/relational-databases/blob/filestream-sql-server)</span></span>|<span data-ttu-id="f8736-136">FILESTREAM 스토리지를 사용하는 시기와 SQL Server 데이터베이스 엔진을 NTFS 파일 시스템과 통합하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-136">Describes when to use FILESTREAM storage and how it integrates the SQL Server Database Engine with an NTFS file system.</span></span>|
|[<span data-ttu-id="f8736-137">FILESTREAM 데이터용 클라이언트 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="f8736-137">Create Client Applications for FILESTREAM Data</span></span>](/sql/relational-databases/blob/create-client-applications-for-filestream-data)|<span data-ttu-id="f8736-138">FILESTREAM 데이터 작업을 위한 Windows API 함수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-138">Describes the Windows API functions for working with FILESTREAM data.</span></span>|
|[<span data-ttu-id="f8736-139">다른 SQL Server 기능과 함께 FILESTREAM 사용</span><span class="sxs-lookup"><span data-stu-id="f8736-139">FILESTREAM and Other SQL Server Features</span></span>](/sql/relational-databases/blob/filestream-compatibility-with-other-sql-server-features)|<span data-ttu-id="f8736-140">FILESTREAM 데이터를 SQL Server의 다른 기능과 함께 사용하기 위한 고려 사항, 지침 및 제한 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f8736-140">Provides considerations, guidelines and limitations for using FILESTREAM data with other features of SQL Server.</span></span>|

## <a name="see-also"></a><span data-ttu-id="f8736-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8736-141">See also</span></span>

- [<span data-ttu-id="f8736-142">SQL Server 데이터 형식 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f8736-142">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="f8736-143">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="f8736-143">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="f8736-144">코드 액세스 보안 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f8736-144">Code Access Security and ADO.NET</span></span>](../code-access-security.md)
- [<span data-ttu-id="f8736-145">SQL Server 이진 및 큰 값 데이터</span><span class="sxs-lookup"><span data-stu-id="f8736-145">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="f8736-146">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="f8736-146">ADO.NET Overview</span></span>](../ado-net-overview.md)
