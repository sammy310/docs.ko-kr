---
description: '자세한 정보: 단일 대량 복사 작업'
title: 단일 대량 복사 작업
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
ms.openlocfilehash: f6b046fbd73ad798f3f9f117eea0b72f46e43b37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767481"
---
# <a name="single-bulk-copy-operations"></a><span data-ttu-id="c4514-103">단일 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="c4514-103">Single Bulk Copy Operations</span></span>

<span data-ttu-id="c4514-104">SQL Server 대량 복사 작업을 수행하는 가장 간단한 방법은 데이터베이스에 대해 단일 작업을 수행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-104">The simplest approach to performing a SQL Server bulk copy operation is to perform a single operation against a database.</span></span> <span data-ttu-id="c4514-105">기본적으로 대량 복사 작업은 격리된 작업으로 수행됩니다. 복사 작업은 트랜잭션되지 않은 방식으로 수행되어 롤백할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-105">By default, a bulk copy operation is performed as an isolated operation: the copy operation occurs in a non-transacted way, with no opportunity for rolling it back.</span></span>

> [!NOTE]
> <span data-ttu-id="c4514-106">오류가 발생하여 대량 복사의 일부 또는 전체를 롤백해야 하는 경우 <xref:System.Data.SqlClient.SqlBulkCopy> 관리형 트랜잭션을 사용하거나 기존 트랜잭션 내에서 대량 복사 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-106">If you need to roll back all or part of the bulk copy when an error occurs, you can either use a <xref:System.Data.SqlClient.SqlBulkCopy>-managed transaction, or perform the bulk copy operation within an existing transaction.</span></span> <span data-ttu-id="c4514-107">연결이 **System.Transactions** 트랜잭션에 암시적으로나 명시적으로 등록된 경우 <xref:System.Transactions>SqlBulkCopy **에서도** 을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-107">**SqlBulkCopy** will also work with <xref:System.Transactions> if the connection is enlisted (implicitly or explicitly) into a **System.Transactions** transaction.</span></span>
>
> <span data-ttu-id="c4514-108">자세한 내용은 [트랜잭션 및 대량 복사 작업](transaction-and-bulk-copy-operations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4514-108">For more information, see [Transaction and Bulk Copy Operations](transaction-and-bulk-copy-operations.md).</span></span>

<span data-ttu-id="c4514-109">대량 복사 작업을 수행하는 일반적인 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-109">The general steps for performing a bulk copy operation are as follows:</span></span>

1. <span data-ttu-id="c4514-110">원본 서버에 연결하고 복사할 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-110">Connect to the source server and obtain the data to be copied.</span></span> <span data-ttu-id="c4514-111"><xref:System.Data.IDataReader> 또는 <xref:System.Data.DataTable> 개체에서 데이터를 검색할 수 있는 경우, 다른 원본에서 데이터를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-111">Data can also come from other sources, if it can be retrieved from an <xref:System.Data.IDataReader> or <xref:System.Data.DataTable> object.</span></span>

2. <span data-ttu-id="c4514-112">**SqlBulkCopy** 를 통해 자동으로 연결하지 않으려는 경우 대상 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-112">Connect to the destination server (unless you want **SqlBulkCopy** to establish a connection for you).</span></span>

3. <span data-ttu-id="c4514-113">필요한 속성을 설정하면서 <xref:System.Data.SqlClient.SqlBulkCopy> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-113">Create a <xref:System.Data.SqlClient.SqlBulkCopy> object, setting any necessary properties.</span></span>

4. <span data-ttu-id="c4514-114">**DestinationTableName** 속성이 대량 삽입 작업의 대상 테이블을 나타내도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-114">Set the **DestinationTableName** property to indicate the target table for the bulk insert operation.</span></span>

5. <span data-ttu-id="c4514-115">**WriteToServer** 메서드 중 하나를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-115">Call one of the **WriteToServer** methods.</span></span>

6. <span data-ttu-id="c4514-116">필요에 따라 속성을 업데이트하고 **WriteToServer** 를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-116">Optionally, update properties and call **WriteToServer** again as necessary.</span></span>

7. <span data-ttu-id="c4514-117"><xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>를 호출하거나 `Using` 문 내에서 대량 복사 작업을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-117">Call <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>, or wrap the bulk copy operations within a `Using` statement.</span></span>

> [!CAUTION]
> <span data-ttu-id="c4514-118">원본 열과 대상 열의 데이터 형식은 일치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-118">We recommend that the source and target column data types match.</span></span> <span data-ttu-id="c4514-119">데이터 형식이 일치하지 않으면 **SqlBulkCopy** 는 <xref:System.Data.SqlClient.SqlParameter.Value%2A>에서 사용되는 규칙과 동일한 규칙을 사용하여 각 원본 값을 대상 데이터 형식으로 변환하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-119">If the data types do not match, **SqlBulkCopy** attempts to convert each source value to the target data type, using the rules employed by <xref:System.Data.SqlClient.SqlParameter.Value%2A>.</span></span> <span data-ttu-id="c4514-120">변환은 성능에 영향을 줄 수 있으며 예기치 않은 오류가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-120">Conversions can affect performance, and also can result in unexpected errors.</span></span> <span data-ttu-id="c4514-121">예를 들어 `Double` 데이터 형식은 대부분의 경우 `Decimal` 데이터 형식으로 변환할 수 있지만 항상 그렇지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-121">For example, a `Double` data type can be converted to a `Decimal` data type most of the time, but not always.</span></span>

## <a name="example"></a><span data-ttu-id="c4514-122">예제</span><span class="sxs-lookup"><span data-stu-id="c4514-122">Example</span></span>

<span data-ttu-id="c4514-123">다음 콘솔 애플리케이션에서는 <xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하여 데이터를 로드하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-123">The following console application demonstrates how to load data using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="c4514-124">이 예제에서는 <xref:System.Data.SqlClient.SqlDataReader>를 사용하여 SQL Server **AdventureWorks** 데이터베이스에 있는 **Production.Product** 테이블의 데이터를 같은 데이터베이스의 비슷한 테이블로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-124">In this example, a <xref:System.Data.SqlClient.SqlDataReader> is used to copy data from the **Production.Product** table in the SQL Server **AdventureWorks** database to a similar table in the same database.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4514-125">[대량 복사 예제 설정](bulk-copy-example-setup.md)에 설명 된 대로 작업 테이블을 만들지 않은 경우이 샘플은 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-125">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](bulk-copy-example-setup.md).</span></span> <span data-ttu-id="c4514-126">이 코드는 **SqlBulkCopy** 를 사용하는 구문을 보여 주는 용도로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-126">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="c4514-127">원본 테이블과 대상 테이블이 동일한 SQL Server 인스턴스에 있으면 Transact-SQL `INSERT … SELECT` 문을 사용하여 데이터를 더 쉽고 빠르게 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-127">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>

[!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
[!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]

## <a name="performing-a-bulk-copy-operation-using-transact-sql-and-the-command-class"></a><span data-ttu-id="c4514-128">Transact-SQL 및 Command 클래스를 사용하여 대량 복사 작업 수행</span><span class="sxs-lookup"><span data-stu-id="c4514-128">Performing a Bulk Copy Operation Using Transact-SQL and the Command Class</span></span>

<span data-ttu-id="c4514-129">다음 예제에서는 <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> 메서드를 사용하여 BULK INSERT 문을 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-129">The following example illustrates how to use the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method to execute the BULK INSERT statement.</span></span>

> [!NOTE]
> <span data-ttu-id="c4514-130">데이터 원본의 파일 경로는 서버에 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-130">The file path for the data source is relative to the server.</span></span> <span data-ttu-id="c4514-131">대량 복사 작업이 성공하려면 서버 프로세스에서 해당 경로에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4514-131">The server process must have access to that path in order for the bulk copy operation to succeed.</span></span>

```vb
Using connection As SqlConnection = New SqlConnection(connectionString)
Dim queryString As String = _
    "BULK INSERT Northwind.dbo.[Order Details] FROM " & _
    "'f:\mydata\data.tbl' WITH (FORMATFILE='f:\mydata\data.fmt' )"
connection.Open()
SqlCommand command = New SqlCommand(queryString, connection);

command.ExecuteNonQuery()
End Using
```

```csharp
using (SqlConnection connection = New SqlConnection(connectionString))
{
string queryString =  "BULK INSERT Northwind.dbo.[Order Details] " +
    "FROM 'f:\mydata\data.tbl' " +
    "WITH ( FORMATFILE='f:\mydata\data.fmt' )";
connection.Open();
SqlCommand command = new SqlCommand(queryString, connection);

command.ExecuteNonQuery();
}
```

## <a name="see-also"></a><span data-ttu-id="c4514-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4514-132">See also</span></span>

- [<span data-ttu-id="c4514-133">SQL Server에서 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="c4514-133">Bulk Copy Operations in SQL Server</span></span>](bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="c4514-134">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="c4514-134">ADO.NET Overview</span></span>](../ado-net-overview.md)
