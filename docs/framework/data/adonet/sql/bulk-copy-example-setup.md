---
title: 대량 복사 예제 설정
ms.date: 03/30/2017
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
ms.openlocfilehash: 6244afff348edbde46fdfda7481910aca2b25939
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117276"
---
# <a name="bulk-copy-example-setup"></a><span data-ttu-id="6d08b-102">대량 복사 예제 설정</span><span class="sxs-lookup"><span data-stu-id="6d08b-102">Bulk Copy Example Setup</span></span>
<span data-ttu-id="6d08b-103"><xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하면 SQL Server 테이블에만 데이터를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d08b-103">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="6d08b-104">SQL Server 예제 데이터베이스를 사용 하 여이 항목에 표시 된 코드 샘플 **AdventureWorks**합니다.</span><span class="sxs-lookup"><span data-stu-id="6d08b-104">The code samples shown in this topic use the SQL Server sample database, **AdventureWorks**.</span></span> <span data-ttu-id="6d08b-105">코드 샘플에서는 기존 테이블을 변경하지 않도록 사용자가 먼저 만드는 테이블에 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="6d08b-105">To avoid altering the existing tables code samples write data to tables that you must create first.</span></span>  
  
 <span data-ttu-id="6d08b-106">합니다 **BulkCopyDemoMatchingColumns** 하 고 **BulkCopyDemoDifferentColumns** 테이블 모두에 기반한 합니다 **AdventureWorks** **Production.Products**  테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="6d08b-106">The **BulkCopyDemoMatchingColumns** and **BulkCopyDemoDifferentColumns** tables are both based on the **AdventureWorks** **Production.Products** table.</span></span> <span data-ttu-id="6d08b-107">이러한 테이블을 사용 하는 코드 샘플에서 데이터에서 추가 되는 **Production.Products** 이러한 샘플 테이블 중 하나에 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="6d08b-107">In code samples that use these tables, data is added from the **Production.Products** table to one of these sample tables.</span></span> <span data-ttu-id="6d08b-108">합니다 **BulkCopyDemoDifferentColumns** 테이블 샘플 원본 데이터의 열을 대상 테이블에 매핑하는 방법을 보여 줍니다 때 사용 됩니다 **BulkCopyDemoMatchingColumns** 대부분의 다른 샘플에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d08b-108">The **BulkCopyDemoDifferentColumns** table is used when the sample illustrates how to map columns from the source data to the destination table; **BulkCopyDemoMatchingColumns** is used for most other samples.</span></span>  
  
 <span data-ttu-id="6d08b-109">일부 코드 샘플에서는 <xref:System.Data.SqlClient.SqlBulkCopy> 클래스 하나로 여러 테이블에 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d08b-109">A few of the code samples demonstrate how to use one <xref:System.Data.SqlClient.SqlBulkCopy> class to write to multiple tables.</span></span> <span data-ttu-id="6d08b-110">이러한 샘플에서는 합니다 **BulkCopyDemoOrderHeader** 하 고 **BulkCopyDemoOrderDetail** 대상 테이블로 테이블을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d08b-110">For these samples, the **BulkCopyDemoOrderHeader** and **BulkCopyDemoOrderDetail** tables are used as the destination tables.</span></span> <span data-ttu-id="6d08b-111">이러한 테이블에 기반한 합니다 **Sales.SalesOrderHeader** 하 고 **Sales.SalesOrderDetail** 테이블 **AdventureWorks**합니다.</span><span class="sxs-lookup"><span data-stu-id="6d08b-111">These tables are based on the **Sales.SalesOrderHeader** and **Sales.SalesOrderDetail** tables in **AdventureWorks**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d08b-112">합니다 **SqlBulkCopy** 코드 샘플은 사용 하는 구문을 보여 주기 위해 제공 됩니다 **SqlBulkCopy** 만 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d08b-112">The **SqlBulkCopy** code samples are provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="6d08b-113">소스 테이블과 대상 테이블이 동일한 SQL Server 인스턴스에 있으면 Transact-SQL `INSERT … SELECT` 문을 사용하여 데이터를 더 쉽고 빠르게 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d08b-113">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
## <a name="table-setup"></a><span data-ttu-id="6d08b-114">테이블 설정</span><span class="sxs-lookup"><span data-stu-id="6d08b-114">Table Setup</span></span>  
 <span data-ttu-id="6d08b-115">코드 샘플을 올바르게 실행하는 데 필요한 테이블을 만들려면 SQL Server 데이터베이스에서 다음 Transact-SQL 문을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d08b-115">To create the tables necessary for the code samples to run correctly, you must run the following Transact-SQL statements in a SQL Server database.</span></span>  
  
```  
USE AdventureWorks  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoMatchingColumns]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoMatchingColumns]  
  
CREATE TABLE [dbo].[BulkCopyDemoMatchingColumns]([ProductID] [int] IDENTITY(1,1) NOT NULL,  
    [Name] [nvarchar](50) NOT NULL,  
    [ProductNumber] [nvarchar](25) NOT NULL,  
 CONSTRAINT [PK_ProductID] PRIMARY KEY CLUSTERED  
(  
    [ProductID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoDifferentColumns]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoDifferentColumns]  
  
CREATE TABLE [dbo].[BulkCopyDemoDifferentColumns]([ProdID] [int] IDENTITY(1,1) NOT NULL,  
    [ProdNum] [nvarchar](25) NOT NULL,  
    [ProdName] [nvarchar](50) NOT NULL,  
 CONSTRAINT [PK_ProdID] PRIMARY KEY CLUSTERED  
(  
    [ProdID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoOrderHeader]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoOrderHeader]  
  
CREATE TABLE [dbo].[BulkCopyDemoOrderHeader]([SalesOrderID] [int] IDENTITY(1,1) NOT NULL,  
    [OrderDate] [datetime] NOT NULL,  
    [AccountNumber] [nvarchar](15) NULL,  
 CONSTRAINT [PK_SalesOrderID] PRIMARY KEY CLUSTERED  
(  
    [SalesOrderID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoOrderDetail]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoOrderDetail]  
  
CREATE TABLE [dbo].[BulkCopyDemoOrderDetail]([SalesOrderID] [int] NOT NULL,  
    [SalesOrderDetailID] [int] NOT NULL,  
    [OrderQty] [smallint] NOT NULL,  
    [ProductID] [int] NOT NULL,  
    [UnitPrice] [money] NOT NULL,  
 CONSTRAINT [PK_LineNumber] PRIMARY KEY CLUSTERED  
(  
    [SalesOrderID] ASC,  
    [SalesOrderDetailID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d08b-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="6d08b-116">See also</span></span>

- [<span data-ttu-id="6d08b-117">SQL Server에서 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="6d08b-117">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="6d08b-118">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="6d08b-118">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
