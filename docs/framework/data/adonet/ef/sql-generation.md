---
title: SQL 생성
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 9c5301d3f4d5bc2e0db4a138c6d8ceb06d3a7845
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854362"
---
# <a name="sql-generation"></a><span data-ttu-id="87f6d-102">SQL 생성</span><span class="sxs-lookup"><span data-stu-id="87f6d-102">SQL Generation</span></span>
<span data-ttu-id="87f6d-103">Entity Framework에 대 한 공급자를 작성 하는 경우 Entity Framework 명령 트리를 특정 데이터베이스가 이해할 수 있는 SQL로 변환 해야 합니다. 예를 들어 Transact-sql은 SQL Server 또는 PL/SQL for Oracle입니다.</span><span class="sxs-lookup"><span data-stu-id="87f6d-103">When you write a provider for the Entity Framework, you must translate Entity Framework command trees into SQL that a specific database can understand, such as Transact-SQL for SQL Server or PL/SQL for Oracle.</span></span> <span data-ttu-id="87f6d-104">이 섹션에서는 Entity Framework 공급자에 대해 SQL 생성 구성 요소 (SELECT 쿼리에 대 한)를 개발 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f6d-104">In this section, you will learn how to develop a SQL generation component (for SELECT queries) for an Entity Framework provider.</span></span> <span data-ttu-id="87f6d-105">Insert, update 및 delete 쿼리에 대 한 자세한 내용은 [수정 SQL 생성](modification-sql-generation.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="87f6d-105">For information about insert, update, and delete queries, see [Modification SQL Generation](modification-sql-generation.md).</span></span>  
  
 <span data-ttu-id="87f6d-106">이 섹션을 이해 하려면 Entity Framework 및 ADO.NET 공급자 모델에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f6d-106">To understand this section, you should be familiar with the Entity Framework and the ADO.NET Provider Model.</span></span> <span data-ttu-id="87f6d-107">또한 명령 트리와 <xref:System.Data.Common.CommandTrees.DbExpression>도 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f6d-107">You should also understand command trees and <xref:System.Data.Common.CommandTrees.DbExpression>.</span></span>  
  
## <a name="the-role-of-the-sql-generation-module"></a><span data-ttu-id="87f6d-108">SQL 생성 모듈의 역할</span><span class="sxs-lookup"><span data-stu-id="87f6d-108">The Role of the SQL Generation Module</span></span>  
 <span data-ttu-id="87f6d-109">Entity Framework 공급자의 SQL 생성 모듈은 지정 된 쿼리 명령 트리를 SQL: 1999 규격 데이터베이스를 대상으로 하는 단일 SQL SELECT 문으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f6d-109">The SQL generation module of an Entity Framework provider translates a given query command tree into a single SQL SELECT statement that targets a SQL:1999-compliant database.</span></span> <span data-ttu-id="87f6d-110">생성된 SQL에는 중첩 쿼리가 가능한 한 적게 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f6d-110">The generated SQL should have as few nested queries as possible.</span></span> <span data-ttu-id="87f6d-111">SQL 생성 모듈은 출력 쿼리 명령 트리를 단순화하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f6d-111">The SQL generation module should not simplify the output query command tree.</span></span> <span data-ttu-id="87f6d-112">예를 들어 조인을 제거 하 고 연속 필터 노드를 축소 하 여이 작업을 수행 합니다. Entity Framework</span><span class="sxs-lookup"><span data-stu-id="87f6d-112">The Entity Framework will do this, for example by eliminating joins and collapsing consecutive filter nodes.</span></span>  
  
 <span data-ttu-id="87f6d-113"><xref:System.Data.Common.DbProviderServices> 클래스는 <xref:System.Data.Common.DbCommand>로 명령 트리를 변환하기 위해 SQL 생성 계층에 액세스할 수 있는 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="87f6d-113">The <xref:System.Data.Common.DbProviderServices> class is the starting point for accessing the SQL generation layer to convert command trees into <xref:System.Data.Common.DbCommand>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="87f6d-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="87f6d-114">In This Section</span></span>  
 [<span data-ttu-id="87f6d-115">명령 트리의 모양</span><span class="sxs-lookup"><span data-stu-id="87f6d-115">The Shape of the Command Trees</span></span>](the-shape-of-the-command-trees.md)  
  
 [<span data-ttu-id="87f6d-116">명령 트리에서 SQL 생성 - 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="87f6d-116">Generating SQL from Command Trees - Best Practices</span></span>](generating-sql-from-command-trees-best-practices.md)  
  
 [<span data-ttu-id="87f6d-117">샘플 공급자의 SQL 생성</span><span class="sxs-lookup"><span data-stu-id="87f6d-117">SQL Generation in the Sample Provider</span></span>](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a><span data-ttu-id="87f6d-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="87f6d-118">See also</span></span>

- [<span data-ttu-id="87f6d-119">Entity Framework 데이터 공급자 작성</span><span class="sxs-lookup"><span data-stu-id="87f6d-119">Writing an Entity Framework Data Provider</span></span>](writing-an-ef-data-provider.md)
