---
title: SQL Server에서 대량 복사 작업
description: SqlBulkCopy 클래스를 사용 하 여 SQL Server 데이터베이스의 테이블이 나 뷰에 대용량 파일을 대량 복사 하는 관리 코드 솔루션을 작성 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: 43d63f3671ea8ff05da3e10580c2784fa3aae581
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197433"
---
# <a name="bulk-copy-operations-in-sql-server"></a><span data-ttu-id="5ebff-103">SQL Server에서 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="5ebff-103">Bulk Copy Operations in SQL Server</span></span>

<span data-ttu-id="5ebff-104">Microsoft SQL Server에는 **bcp**라는 많이 사용되는 명령줄 유틸리티가 있어 SQL Server 데이터베이스의 테이블이나 뷰로 큰 파일을 신속하게 대량 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ebff-104">Microsoft SQL Server includes a popular command-line utility named **bcp** for quickly bulk copying large files into tables or views in SQL Server databases.</span></span> <span data-ttu-id="5ebff-105"><xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하면 비슷한 기능을 제공하는 관리 코드 솔루션을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ebff-105">The <xref:System.Data.SqlClient.SqlBulkCopy> class allows you to write managed code solutions that provide similar functionality.</span></span> <span data-ttu-id="5ebff-106">INSERT 문과 같은 다른 방법을 사용하여 데이터를 SQL Server 테이블에 로드할 수 있지만 <xref:System.Data.SqlClient.SqlBulkCopy>는 훨씬 더 향상된 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebff-106">There are other ways to load data into a SQL Server table (INSERT statements, for example) but <xref:System.Data.SqlClient.SqlBulkCopy> offers a significant performance advantage over them.</span></span>  
  
 <span data-ttu-id="5ebff-107"><xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하면 SQL Server 테이블에만 데이터를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ebff-107">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="5ebff-108">그러나 데이터 소스가 SQL Server로 제한되어 있지 않으므로 데이터를 <xref:System.Data.DataTable> 인스턴스로 로드하거나 <xref:System.Data.IDataReader> 인스턴스를 사용하여 읽을 수 있으면 모든 데이터 소스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ebff-108">But the data source is not limited to SQL Server; any data source can be used, as long as the data can be loaded to a <xref:System.Data.DataTable> instance or read with a <xref:System.Data.IDataReader> instance.</span></span>  
  
 <span data-ttu-id="5ebff-109"><xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ebff-109">Using the <xref:System.Data.SqlClient.SqlBulkCopy> class, you can perform:</span></span>  
  
- <span data-ttu-id="5ebff-110">단일 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="5ebff-110">A single bulk copy operation</span></span>  
  
- <span data-ttu-id="5ebff-111">여러 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="5ebff-111">Multiple bulk copy operations</span></span>  
  
- <span data-ttu-id="5ebff-112">트랜잭션 내의 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="5ebff-112">A bulk copy operation within a transaction</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5ebff-113"><xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 지원하지 않는 .NET Framework 버전 1.1 이하를 사용하는 경우 **개체를 사용하여 SQL Server Transact-SQL**BULK INSERT<xref:System.Data.SqlClient.SqlCommand> 문을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ebff-113">When using .NET Framework version 1.1 or earlier (which does not support the <xref:System.Data.SqlClient.SqlBulkCopy> class), you can execute the SQL Server Transact-SQL **BULK INSERT** statement using the <xref:System.Data.SqlClient.SqlCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5ebff-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="5ebff-114">In This Section</span></span>  

 [<span data-ttu-id="5ebff-115">대량 복사 예제 설정</span><span class="sxs-lookup"><span data-stu-id="5ebff-115">Bulk Copy Example Setup</span></span>](bulk-copy-example-setup.md)  
 <span data-ttu-id="5ebff-116">대량 복사 예제에 사용된 테이블에 대해 설명하고 AdventureWorks 데이터베이스에서 테이블을 만들기 위한 SQL 스크립트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebff-116">Describes the tables used in the bulk copy examples and provides SQL scripts for creating the tables in the AdventureWorks database.</span></span>  
  
 [<span data-ttu-id="5ebff-117">단일 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="5ebff-117">Single Bulk Copy Operations</span></span>](single-bulk-copy-operations.md)  
 <span data-ttu-id="5ebff-118"><xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하여 SQL Server 인스턴스에 데이터의 단일 대량 복사를 수행하는 방법 및 Transact-SQL 문과 <xref:System.Data.SqlClient.SqlCommand> 클래스를 사용하여 대량 복사 작업을 수행하는 방법을 각각 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebff-118">Describes how to do a single bulk copy of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class, and how to perform the bulk copy operation using Transact-SQL statements and the <xref:System.Data.SqlClient.SqlCommand> class.</span></span>  
  
 [<span data-ttu-id="5ebff-119">여러 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="5ebff-119">Multiple Bulk Copy Operations</span></span>](multiple-bulk-copy-operations.md)  
 <span data-ttu-id="5ebff-120"><xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하여 SQL Server 인스턴스에 데이터의 여러 대량 복사 작업을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebff-120">Describes how to do multiple bulk copy operations of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span>  
  
 [<span data-ttu-id="5ebff-121">트랜잭션 및 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="5ebff-121">Transaction and Bulk Copy Operations</span></span>](transaction-and-bulk-copy-operations.md)  
 <span data-ttu-id="5ebff-122">트랜잭션을 커밋하거나 롤백하는 방법을 포함해 트랜잭션 내에서 대량 복사 작업을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebff-122">Describes how to perform a bulk copy operation within a transaction, including how to commit or rollback the transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ebff-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ebff-123">See also</span></span>

- [<span data-ttu-id="5ebff-124">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5ebff-124">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="5ebff-125">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="5ebff-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
