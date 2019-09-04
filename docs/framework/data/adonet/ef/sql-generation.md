---
title: SQL 생성
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 2c18e88967fcba2b8414bfc171412eba908002b3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248409"
---
# <a name="sql-generation"></a><span data-ttu-id="14ac3-102">SQL 생성</span><span class="sxs-lookup"><span data-stu-id="14ac3-102">SQL Generation</span></span>
<span data-ttu-id="14ac3-103">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]의 공급자를 작성할 때 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 명령 트리를 특정 데이터베이스가 이해할 수 있는 SQL(예: SQL Server의 경우 Transact-SQL, Oracle의 경우 PL/SQL)로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14ac3-103">When you write a provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you must translate [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] command trees into SQL that a specific database can understand, such as Transact-SQL for SQL Server or PL/SQL for Oracle.</span></span> <span data-ttu-id="14ac3-104">이 단원에서는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 공급자에 대한 SQL 생성 구성 요소(SELECT 쿼리의 경우)를 개발하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="14ac3-104">In this section, you will learn how to develop a SQL generation component (for SELECT queries) for an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider.</span></span> <span data-ttu-id="14ac3-105">Insert, update 및 delete 쿼리에 대 한 자세한 내용은 [수정 SQL 생성](modification-sql-generation.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14ac3-105">For information about insert, update, and delete queries, see [Modification SQL Generation](modification-sql-generation.md).</span></span>  
  
 <span data-ttu-id="14ac3-106">이 단원을 이해하려면 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 및 ADO.NET 공급자 모델에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14ac3-106">To understand this section, you should be familiar with the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and the ADO.NET Provider Model.</span></span> <span data-ttu-id="14ac3-107">또한 명령 트리와 <xref:System.Data.Common.CommandTrees.DbExpression>도 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14ac3-107">You should also understand command trees and <xref:System.Data.Common.CommandTrees.DbExpression>.</span></span>  
  
## <a name="the-role-of-the-sql-generation-module"></a><span data-ttu-id="14ac3-108">SQL 생성 모듈의 역할</span><span class="sxs-lookup"><span data-stu-id="14ac3-108">The Role of the SQL Generation Module</span></span>  
 <span data-ttu-id="14ac3-109">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 공급자의 SQL 생성 모듈은 지정된 쿼리 명령 트리를 SQL:1999 규격 데이터베이스를 대상으로 하는 단일 SQL SELECT 문으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="14ac3-109">The SQL generation module of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider translates a given query command tree into a single SQL SELECT statement that targets a SQL:1999-compliant database.</span></span> <span data-ttu-id="14ac3-110">생성된 SQL에는 중첩 쿼리가 가능한 한 적게 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14ac3-110">The generated SQL should have as few nested queries as possible.</span></span> <span data-ttu-id="14ac3-111">SQL 생성 모듈은 출력 쿼리 명령 트리를 단순화하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14ac3-111">The SQL generation module should not simplify the output query command tree.</span></span> <span data-ttu-id="14ac3-112">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]는 조인을 제거하고 연속 필터 노드를 축소하는 등의 작업을 통해 이를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="14ac3-112">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] will do this, for example by eliminating joins and collapsing consecutive filter nodes.</span></span>  
  
 <span data-ttu-id="14ac3-113"><xref:System.Data.Common.DbProviderServices> 클래스는 <xref:System.Data.Common.DbCommand>로 명령 트리를 변환하기 위해 SQL 생성 계층에 액세스할 수 있는 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="14ac3-113">The <xref:System.Data.Common.DbProviderServices> class is the starting point for accessing the SQL generation layer to convert command trees into <xref:System.Data.Common.DbCommand>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14ac3-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="14ac3-114">In This Section</span></span>  
 [<span data-ttu-id="14ac3-115">명령 트리의 모양</span><span class="sxs-lookup"><span data-stu-id="14ac3-115">The Shape of the Command Trees</span></span>](the-shape-of-the-command-trees.md)  
  
 [<span data-ttu-id="14ac3-116">명령 트리에서 SQL 생성 - 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="14ac3-116">Generating SQL from Command Trees - Best Practices</span></span>](generating-sql-from-command-trees-best-practices.md)  
  
 [<span data-ttu-id="14ac3-117">샘플 공급자의 SQL 생성</span><span class="sxs-lookup"><span data-stu-id="14ac3-117">SQL Generation in the Sample Provider</span></span>](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a><span data-ttu-id="14ac3-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="14ac3-118">See also</span></span>

- [<span data-ttu-id="14ac3-119">Entity Framework 데이터 공급자 작성</span><span class="sxs-lookup"><span data-stu-id="14ac3-119">Writing an Entity Framework Data Provider</span></span>](writing-an-ef-data-provider.md)
