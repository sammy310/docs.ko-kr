---
description: '자세한 정보: 트랜잭션 및 동시성'
title: 트랜잭션 및 동시성
ms.date: 03/30/2017
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
ms.openlocfilehash: c77b9abc72ae662eec76fc40a9856ad73f000c27
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766766"
---
# <a name="transactions-and-concurrency"></a><span data-ttu-id="75c1e-103">트랜잭션 및 동시성</span><span class="sxs-lookup"><span data-stu-id="75c1e-103">Transactions and Concurrency</span></span>

<span data-ttu-id="75c1e-104">트랜잭션은 패키지로 실행되는 하나의 명령 또는 명령 그룹으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="75c1e-104">A transaction consists of a single command or a group of commands that execute as a package.</span></span> <span data-ttu-id="75c1e-105">트랜잭션을 사용하여 여러 작업을 하나의 작업 단위로 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75c1e-105">Transactions allow you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="75c1e-106">또한 트랜잭션의 한 지점에서 오류가 발생하는 경우 모든 업데이트를 이전 트랜잭션 상태로 롤백할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75c1e-106">If a failure occurs at one point in the transaction, all of the updates can be rolled back to their pre-transaction state.</span></span>  
  
 <span data-ttu-id="75c1e-107">트랜잭션은 데이터 일관성을 유지하기 위해 Atomicity(원자성), Consistency(일관성), Isolation(격리성) 및 Durability(영속성)를 나타내는 ACID 속성을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75c1e-107">A transaction must conform to the ACID properties—atomicity, consistency, isolation, and durability—in order to guarantee data consistency.</span></span> <span data-ttu-id="75c1e-108">Microsoft SQL Server 같은 대부분의 관계형 데이터베이스 시스템에서는 클라이언트 애플리케이션이 작업을 업데이트, 삽입 또는 삭제할 때마다 잠금, 로깅 및 트랜잭션 관리 기능을 제공하여 트랜잭션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="75c1e-108">Most relational database systems, such as Microsoft SQL Server, support transactions by providing locking, logging, and transaction management facilities whenever a client application performs an update, insert, or delete operation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75c1e-109">잠금이 너무 길게 유지되면 트랜잭션에 여러 리소스가 관여하는 경우 동시성이 낮아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75c1e-109">Transactions that involve multiple resources can lower concurrency if locks are held too long.</span></span> <span data-ttu-id="75c1e-110">따라서 트랜잭션은 가능한 한 짧게 유지하세요.</span><span class="sxs-lookup"><span data-stu-id="75c1e-110">Therefore, keep transactions as short as possible.</span></span>  
  
 <span data-ttu-id="75c1e-111">같은 데이터베이스나 서버에 여러 테이블이 있는 트랜잭션의 경우에는 저장 프로시저의 명시적 트랜잭션이 더 효과적으로 수행되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="75c1e-111">If a transaction involves multiple tables in the same database or server, then explicit transactions in stored procedures often perform better.</span></span> <span data-ttu-id="75c1e-112">SQL Server 저장 프로시저에서는 Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION` 및 `ROLLBACK TRANSACTION` 문을 사용하여 트랜잭션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75c1e-112">You can create transactions in SQL Server stored procedures by using the Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION`, and `ROLLBACK TRANSACTION` statements.</span></span> <span data-ttu-id="75c1e-113">자세한 내용은 SQL Server 온라인 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="75c1e-113">For more information, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="75c1e-114">SQL Server와 Oracle 간 트랜잭션 같은 여러 리소스 관리자가 관련된 트랜잭션에는 분산 트랜잭션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="75c1e-114">Transactions involving different resource managers, such as a transaction between SQL Server and Oracle, require a distributed transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="75c1e-115">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="75c1e-115">In This Section</span></span>  

 [<span data-ttu-id="75c1e-116">로컬 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="75c1e-116">Local Transactions</span></span>](local-transactions.md)  
 <span data-ttu-id="75c1e-117">데이터베이스에 대해 트랜잭션을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="75c1e-117">Demonstrates how to perform transactions against a database.</span></span>  
  
 [<span data-ttu-id="75c1e-118">분산 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="75c1e-118">Distributed Transactions</span></span>](distributed-transactions.md)  
 <span data-ttu-id="75c1e-119">ADO.NET에서 분산 트랜잭션을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="75c1e-119">Describes how to perform distributed transactions in ADO.NET.</span></span>  
  
 [<span data-ttu-id="75c1e-120">SQL Server와의 시스템 트랜잭션 통합</span><span class="sxs-lookup"><span data-stu-id="75c1e-120">System.Transactions Integration with SQL Server</span></span>](system-transactions-integration-with-sql-server.md)  
 <span data-ttu-id="75c1e-121">분산 트랜잭션 작업을 위한 <xref:System.Transactions>와 SQL Server 간 통합을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="75c1e-121">Describes <xref:System.Transactions> integration with SQL Server for working with distributed transactions.</span></span>  
  
 [<span data-ttu-id="75c1e-122">낙관적 동시성</span><span class="sxs-lookup"><span data-stu-id="75c1e-122">Optimistic Concurrency</span></span>](optimistic-concurrency.md)  
 <span data-ttu-id="75c1e-123">낙관적 및 비관적 동시성에 대해 설명하고 동시성 위반을 테스트하는 방법에 대해 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="75c1e-123">Describes optimistic and pessimistic concurrency, and how you can test for concurrency violations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75c1e-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75c1e-124">See also</span></span>

- [<span data-ttu-id="75c1e-125">트랜잭션 기본 사항</span><span class="sxs-lookup"><span data-stu-id="75c1e-125">Transaction Fundamentals</span></span>](../transactions/transaction-fundamentals.md)
- [<span data-ttu-id="75c1e-126">데이터 소스에 연결</span><span class="sxs-lookup"><span data-stu-id="75c1e-126">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="75c1e-127">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="75c1e-127">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="75c1e-128">DataAdapters 및 DataReaders</span><span class="sxs-lookup"><span data-stu-id="75c1e-128">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="75c1e-129">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="75c1e-129">DbProviderFactories</span></span>](dbproviderfactories.md)
- [<span data-ttu-id="75c1e-130">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="75c1e-130">ADO.NET Overview</span></span>](ado-net-overview.md)
